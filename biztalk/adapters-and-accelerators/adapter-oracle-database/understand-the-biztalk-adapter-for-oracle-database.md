---
title: Comprender el adaptador de BizTalk para Oracle Database | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fda25d77571a3c0128317a557e5f9d15bbc472
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994621"
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a>Comprender el adaptador de BizTalk para Oracle Database
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
- **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño comunes y fácil de usar para explorar, buscar y recuperar los metadatos de artefactos de LOB.  
  
- **Variar las opciones de programación**. Los adaptadores proporcionan una elección del modelo de programación incluido el modelo de canal de Windows Communication Foundation (WCF), WCF del servicio servicios Web de model, ADO.NET, o modelos admitidos de BizTalk.  
  
- **Uniforme de experiencia en LOB**. Los adaptadores de estandarizan sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y por lo tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
  Como se mencionó, los adaptadores se crean sobre el SDK de adaptador LOB de WCF. El SDK de adaptador LOB de WCF proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones de cliente como el servidor BizTalk Server y Microsoft Office. El SDK de adaptador LOB de WCF se alinea a la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de los adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre el SDK de adaptador LOB de WCF, vea [documentación del SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).
  
  Para llevar a cabo operaciones en una base de datos de Oracle, los clientes del adaptador deben tener acceso a las tablas relevantes, funciones y procedimientos. Las tablas de base de datos son la unidad básica de almacenamiento en la base de datos de Oracle. Las aplicaciones externas se pueden agregar o quitar datos de una tabla mediante el uso de instrucciones SQL. Las aplicaciones también pueden tener acceso a datos en las tablas mediante el uso de vistas, funciones y procedimientos. Con [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], los clientes del adaptador pueden examinar los artefactos, como tablas, procedimientos, paquetes, vistas y otros elementos de este tipo en una base de datos de Oracle. Los clientes del adaptador pueden seleccionar los artefactos que se requieren para su solución y recuperar metadatos para aquellos artefactos. Esto permite a los usuarios obtener acceso a ejecutar las operaciones en los artefactos en la base de datos de Oracle.  
  
  En esta sección se enumera las características de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [Características clave en el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [Limitaciones del adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a>Vea también  
[Introducción a BizTalk Server](../../core/getting-started-with-biztalk-server.md)