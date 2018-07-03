---
title: Desarrollar aplicaciones de BizTalk con el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Content-Based Routing (CBR)
- BizTalk orchestrations, using orchestrations to perform operations
ms.assetid: 65689c83-4a57-4aad-b0e9-f1bad901a7b9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05b342de0cb2bf7d99cf50774bedb81f36f82d9c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002365"
---
# <a name="develop-biztalk-applications-using-the-oracle-database-adapter"></a>Desarrollar aplicaciones de BizTalk con el adaptador de base de datos de Oracle
Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y el uso de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar el esquema XML. Una vez que haya generado el esquema, puede usar el enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir los mensajes que cumplen el esquema generado.  
  
 CBR puede usarse en escenarios donde los mensajes que se envían a la base de datos de Oracle no requieren ningún procesamiento intensivo. Por ejemplo, si sabe que el puerto de recepción va a recibir los mensajes solo de un tipo determinado, puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.  
  
 En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Esta sección proporciona información acerca de cómo utilizar orquestaciones de BizTalk para realizar operaciones en la base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que puede interactuar con un enlace WCF.  
  
> [!IMPORTANT]
>  Para usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre se debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**. Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
> 
> [!IMPORTANT]
>  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] incluido con [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparece en la consola de administración de BizTalk Server. Los adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] están basados en WCF y utilizar un enlace personalizado de WCF. La consola de administración de BizTalk Server muestra el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]. No lo hace automáticamente para mostrar los enlaces personalizados de WCF y, por tanto, no se muestra el WCF basado [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
> 
> Además, para generar los metadatos, use el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]. No use el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Para obtener instrucciones sobre el uso de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md). 
> 
> Para conocer otras diferencias entre las versiones de adaptador, vea [migrar BizTalk proyectos creó el adaptador de BizTalk ODBC para Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).  
  
  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)