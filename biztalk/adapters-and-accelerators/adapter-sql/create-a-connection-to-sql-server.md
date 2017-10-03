---
title: "Crear una conexión a SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b87b4141c9e14c680d8100a7c505dda0a0093c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-sql-server"></a>Crear una conexión a SQL Server
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, habilita la comunicación con una base de datos de SQL Server a través de una dirección de extremo WCF. En WCF, la dirección del extremo identifica la ubicación de un servicio de red y normalmente se expresa como un identificador uniforme de recursos (URI). El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se utiliza para establecer una conexión con la base de datos de SQL Server. Debe especificar un URI de conexión al que:  
  
-   Crear un generador de canales o un agente de escucha del canal mediante el modelo de canal WCF o cuando se crea un host de servicio o cliente WCF mediante el modelo de servicio WCF.  
  
-   Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
-   Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para una solución de BizTalk Server.  
  
-   Usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
 Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] y la base de datos de SQL Server al proporcionarle con:  
  
-   Información sobre las propiedades de conexión y la estructura del URI de conexión de SQL Server.  
  
-   Vínculos a temas que muestran cómo especificar un URI de conexión mediante el uso de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
-   Obtener información sobre cómo conectarse a SQL Server mediante autenticación de Windows.  
  
  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)