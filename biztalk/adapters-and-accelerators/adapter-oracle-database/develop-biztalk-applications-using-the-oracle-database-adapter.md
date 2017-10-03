---
title: Desarrollar aplicaciones de BizTalk con el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Content-Based Routing (CBR)
- BizTalk orchestrations, using orchestrations to perform operations
ms.assetid: 65689c83-4a57-4aad-b0e9-f1bad901a7b9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1b3f688987c0c8339a2fd81c1b1ddf67128818
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-oracle-database-adapter"></a>Desarrollar aplicaciones de BizTalk con el adaptador de la base de datos de Oracle
Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y el uso de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar el esquema XML. Una vez que haya generado el esquema, puede usar enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir mensajes que cumplen el esquema generado.  
  
 CBR puede utilizarse en escenarios donde los mensajes se envíen a la base de datos de Oracle no requieren ningún procesamiento intensivo. Por ejemplo, si sabe que el puerto de recepción va a recibir mensajes sólo de un tipo determinado, puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.  
  
 En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Esta sección proporciona información sobre el uso de las orquestaciones de BizTalk para realizar operaciones en la base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que puede interactuar con un enlace de WCF.  
  
> [!IMPORTANT]
>  Para usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre se debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
> [!IMPORTANT]
>  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] incluido con [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparece en la consola de administración de BizTalk Server. Los adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] están basadas en WCF y utilizar un enlace personalizado de WCF. La consola de administración de BizTalk Server muestra la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]. Que no mostrar automáticamente los enlaces personalizados de WCF y, por tanto, no se muestra el WCF basado [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
> 
> Además, para generar metadatos, use el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]. No use el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Para obtener instrucciones sobre cómo utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md). 
> 
> Si hay otras diferencias entre las versiones de adaptador, vea [migrar BizTalk proyectos creado mediante el adaptador de BizTalk ODBC para la base de datos de Oracle](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).  
  
  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)