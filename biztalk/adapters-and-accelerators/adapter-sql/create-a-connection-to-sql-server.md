---
title: Crear una conexión a SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7c5f186a28f068f3ffc217ce5f252a1512f03a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978013"
---
# <a name="create-a-connection-to-sql-server"></a>Crear una conexión a SQL Server
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, permite la comunicación a una base de datos de SQL Server a través de una dirección de extremo WCF. En WCF, la dirección del punto de conexión identifica la ubicación de un servicio de red y normalmente se expresa como un identificador uniforme de recursos (URI). El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utiliza para establecer una conexión a la base de datos de SQL Server. Debe especificar un URI de conexión cuando le:  
  
- Crear un generador de canales o un agente de escucha del canal mediante el modelo de canal WCF o al crear un host de servicio o cliente WCF mediante el modelo de servicio WCF.  
  
- Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
- Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje desde el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para una solución de BizTalk Server.  
  
- Utilice la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
  Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] y la base de datos de SQL Server al proporcionarle con:  
  
- Información sobre las propiedades de conexión y la estructura de lo URI de conexión de SQL Server.  
  
- Vínculos a temas que muestran cómo especificar un URI de conexión mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
- Información sobre cómo conectarse a SQL Server mediante autenticación de Windows.  
  
  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)