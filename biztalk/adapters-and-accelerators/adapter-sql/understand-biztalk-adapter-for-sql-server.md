---
title: Comprender el adaptador de BizTalk para SQL Server | Documentos de Microsoft
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
ms.openlocfilehash: 3fc14b7d9da40edd56c4c4cc4fa6b795386518db
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965306"
---
# <a name="understand-biztalk-adapter-for-sql-server"></a>Comprender el adaptador de BizTalk para SQL Server
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios lo que permite interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
-   **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño común y fácil de usar para la exploración, búsqueda y recuperación de metadatos de artefactos de LOB.  
  
-   **Opciones de programación de variados**. Los adaptadores proporcionan servicios Web ADO.NET, modelo de servicio de una opción de modelo de programación incluido el modelo de canal de Windows Communication Foundation (WCF), WCF o BizTalk admite modelos.  
  
-   **Uniformes experiencia a través de LOB**. Los adaptadores estandarización sobre el uso de WCF y la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y por lo tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
 Como se mencionó, los adaptadores se generan en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones cliente como el servidor BizTalk Server y Microsoft Office. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Alinee la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], consulte el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación está instalada junto con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], normalmente en \<unidad de instalación\>: \Program archivos\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.  
  
 Para llevar a cabo operaciones en una base de datos de SQL Server, los clientes de adaptador deben tener acceso a tablas relevantes, procedimientos, vistas, funciones escalares y funciones con valores de tabla. Tablas de base de datos son la unidad básica de almacenamiento en la base de datos de SQL Server. Las aplicaciones externas pueden seleccionar, insertar, eliminar y actualizar los datos de una tabla mediante instrucciones SQL. Las aplicaciones también pueden tener acceso a datos en las tablas mediante el uso de procedimientos, vistas, funciones escalares y funciones con valores de tabla. Con [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], los clientes de adaptador pueden examinar artefactos, como tablas, procedimientos, vistas y otros elementos de este tipo en una base de datos de SQL Server. Los clientes de adaptador pueden seleccionar los artefactos que necesitan para su solución y recuperar los metadatos de los artefactos. Esto permite a los usuarios tener acceso y ejecutar las operaciones en los artefactos en la base de datos de SQL Server.  
  
 En esta sección se enumera las características de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)  
  
-   [Características clave en el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/key-features-in-biztalk-adapter-for-sql-server.md) 
  
-   [Limitaciones del adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/limitations-of-biztalk-adapter-for-sql-server.md)  
  
## <a name="see-also"></a>Vea también  
[Empezar a trabajar con el adaptador de BizTalk para SQL](../../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)