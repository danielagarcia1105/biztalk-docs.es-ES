---
title: Desarrollar aplicaciones de BizTalk con el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 08/02/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
- CBR
- Content-Based Routing
ms.assetid: 1a2a9765-305c-44b2-aed7-5437725e4c19
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8267c07027d9994b0115ebaf49fde96e76f2716
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-siebel-adapter"></a>Desarrollar aplicaciones de BizTalk con el adaptador de Siebel

## <a name="overview"></a>Información general
Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y el uso de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar el esquema XML. Una vez que haya generado el esquema, puede usar enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir mensajes que cumplen el esquema generado.  
  
 CBR puede utilizarse en escenarios donde los mensajes se envíen a un sistema Siebel no requieren ningún procesamiento intensivo. Por ejemplo, si sabe que el puerto de recepción va a recibir mensajes sólo de un tipo determinado, puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.  
  
 En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Esta sección proporciona información sobre el uso de las orquestaciones de BizTalk para realizar operaciones en un sistema Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] que puede interactuar con un enlace de WCF.  

## <a name="before-you-begin"></a>Antes de empezar  

* Para usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establezca siempre la **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**. Para conocer los pasos, consulte [configurar las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).
  
* El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no se mostrará automáticamente en la consola de administración de BizTalk Server. Esto es porque el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es un enlace personalizado de WCF. 

* Para generar los metadatos, use el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]. No use el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Para obtener instrucciones sobre cómo utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).   

  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)