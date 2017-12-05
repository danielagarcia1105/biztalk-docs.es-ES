---
title: Comprender el adaptador de BizTalk para base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF LOB Adapter SDK
- features of Oracle database adapter
- table
- adapter client
- service model
- WCF
- artifacts
- database tables
- adapters, features
- Windows Communication Foundation
- adapter features
- channel model
ms.assetid: a8691957-0430-4cba-83f8-b60c21a86849
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb2d3603bb6d7c64d355c88420167344f564ddd8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a>Comprender el adaptador de BizTalk para base de datos de Oracle
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
-   **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño común y fácil de usar para la exploración, búsqueda y recuperación de metadatos de artefactos de LOB.  
  
-   **Opciones de programación de variados**. Los adaptadores proporcionan servicios Web ADO.NET, modelo de servicio de una opción de modelo de programación incluido el modelo de canal de Windows Communication Foundation (WCF), WCF o BizTalk admite modelos.  
  
-   **Uniformes experiencia a través de LOB**. Los adaptadores estandarización sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y por lo tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
 Como se mencionó, los adaptadores se generan en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones cliente como el servidor BizTalk Server y Microsoft Office. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Alinee la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], consulte el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación está instalada junto con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], normalmente en \<unidad de instalación\>: \Program archivos\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.  
  
 Para llevar a cabo operaciones en una base de datos de Oracle, los clientes de adaptador deben tener acceso a tablas relevantes, funciones y procedimientos. Tablas de base de datos son la unidad básica de almacenamiento en la base de datos de Oracle. Las aplicaciones externas pueden agregar o quitar datos de una tabla mediante instrucciones SQL. Las aplicaciones también pueden tener acceso a datos en las tablas mediante el uso de vistas, funciones y procedimientos. Con [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], los clientes de adaptador pueden examinar los artefactos, como tablas, procedimientos, paquetes, vistas y otros elementos de este tipo en una base de datos de Oracle. Los clientes de adaptador pueden seleccionar los artefactos que necesitan para su solución y recuperan metadatos para los artefactos. Esto permite a los usuarios tener acceso y ejecutar las operaciones en los artefactos en la base de datos de Oracle.  
  
 En esta sección se enumera las características de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [Características clave en el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [Limitaciones del adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a>Vea también  
[Introducción a BizTalk Server](../../core/getting-started-with-biztalk-server.md)