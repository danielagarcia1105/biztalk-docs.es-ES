---
title: Con BizTalk Server y el SDK del adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43ff0357-76e6-42bc-a1f7-0385d9378a5f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41fffdf81d6e5565f9799594ddee485be485fed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226020"
---
# <a name="using-biztalk-server-and-the-wcf-lob-adapter-sdk"></a>Con BizTalk Server y el SDK del adaptador LOB de WCF
Esta sección contiene información sobre la relación de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. La información contenida en esta sección incluye las comparaciones de los dos marcos diferentes proporcionadas por cada uno de ellos y sugerencias para migrar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador personalizado.  
  
## <a name="relationship-with-the-sdk-and-biztalk-server"></a>Relación con el SDK y el servidor de BizTalk
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]Proporciona un SDK y el conjunto de herramientas y componentes que permiten a los desarrolladores escribir adaptadores sofisticados para los sistemas de línea de negocio que contiene un conjunto dinámico de las operaciones y datos. Los adaptadores se exponen como enlaces personalizados de WCF y por lo tanto, pueden utilizarse en aplicaciones que pueden consumir los enlaces de WCF.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]es un producto que permite el flujo de mensajes y la coordinación entre un conjunto diverso de los sistemas empresariales; comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y sistemas externos se controlan a través de adaptadores que toman los mensajes externos y transforman en un formato adecuado para su procesamiento mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 Estas dos tecnologías que forman una intersección en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador de WCF. Puede usar enlaces expuestos por WCF y consumir, por tanto, las operaciones y los datos expuestos por el adaptador escrito con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
 Las ilustraciones siguientes se proporciona información general de cómo se utilizan los adaptadores LOB de WCF y el adaptador de WCF de BizTalk en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para comunicarse con sistemas LOB de destino.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8dd622c6-ab5e-4cd9-aa86-5176f5c62203.gif "8dd622c6-ab5e-4cd9-aa86-5176f5c62203")  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4f503084-da4f-41cb-92b9-eaea25d1b456.gif "4f503084-da4f-41cb-92b9-eaea25d1b456")  

## <a name="differences-between-the-sdk-and-the-biztalk-server-adapter-framework"></a>Diferencias entre el SDK y el marco de trabajo del adaptador de BizTalk Server

Mientras tanto la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] marco de trabajo proporcionan un SDK para escribir adaptadores personalizados, existe son diferencias significativas en la cantidad de soporte técnico proporcionada en cuanto a la API y las herramientas y también en la reutilización del adaptador una vez es completado.  
  
 En la tabla siguiente se resumen algunas de las diferencias principales entre los dos marcos.  
  
|Característica|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Marco de trabajo|  
|---|---|---|  
|API|[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]y [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)] ensamblado, proporciona las clases de ayuda para los metadatos de procesamiento, administración de conexiones y la mensajería|COM, proporciona compatibilidad básica para las operaciones del adaptador.|  
|Exposición de adaptador|Exponer como enlace de WCF; está disponible para cualquier aplicación que puede consumir un enlace WCF.|Expone solo a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]; no reutilizable para otras aplicaciones.|  
|Herramientas|[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)], Explorador de metadatos para[!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]|n/d|  
|Extensibilidad|Sí (como extensión de canal WCF)|No|  
  
 Adaptadores creados mediante el marco de trabajo del adaptador de BizTalk son dese solo en BizTalk Server. Por otro lado, los adaptadores que se escriben en el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparecen como enlaces de WCF personalizados. Esto amplía su alcance para cualquier aplicación que consume un servicio, que, por razones prácticas, es cualquier .NET incluidos aplicación [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Los adaptadores basados en WCF se utilizan dentro de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de WCF de BizTalk y continúan existiendo en paralelo con los adaptadores nativos de BizTalk. 
 
