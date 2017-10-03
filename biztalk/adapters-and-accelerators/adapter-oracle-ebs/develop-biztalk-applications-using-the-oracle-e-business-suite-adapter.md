---
title: Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf3374a2-2fca-4df4-a1b1-d11cdc05d393
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d201987490d9395b07d043c67fa50a31400fe7cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-oracle-e-business-suite-adapter"></a>Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite
Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y el uso de la  **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]**  o  **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]**  para generar el esquema XML. Una vez que haya generado el esquema, puede usar enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir mensajes que cumplen el esquema generado.  
  
 CBR puede utilizarse en escenarios donde los mensajes se envíen a Oracle E-Business Suite no requieren ningún procesamiento intensivo. Por ejemplo, si sabe que los mensajes de recepción del puerto de recepción solo de un tipo determinado, se puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.  

## <a name="use-orchestration"></a>Orquestación de uso  
 En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. 
 
 Esta sección proporciona información sobre el uso de las orquestaciones de BizTalk para realizar tareas y operaciones sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)]. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que puede interactuar con un enlace de WCF.  
  
> [!IMPORTANT]
>  Para usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre se debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**. Para conocer los pasos, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).  
  

  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)