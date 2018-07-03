---
title: Uso de BizTalk Server y el SDK del adaptador LOB de WCF | Microsoft Docs
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
ms.openlocfilehash: 46b06f832fd9ff36f0e274c1599b577bc9ec6010
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989981"
---
# <a name="using-biztalk-server-and-the-wcf-lob-adapter-sdk"></a>Uso de BizTalk Server y el SDK del adaptador LOB de WCF
Esta sección contiene información sobre la relación de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. La información contenida en esta sección incluye comparaciones de los dos marcos diferentes proporcionados por cada uno y sugerencias para migrar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador personalizado.  

## <a name="relationship-with-the-sdk-and-biztalk-server"></a>Relación con el SDK y el servidor BizTalk Server
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Proporciona un SDK y el conjunto de herramientas y componentes que permiten a los programadores escribir sofisticados adaptadores para los sistemas de línea de negocio que contiene un conjunto dinámico de datos y las operaciones. Los adaptadores se exponen como enlaces personalizados de WCF y por lo tanto, pueden utilizarse en aplicaciones que pueden consumir los enlaces de WCF.  

 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] es un producto que permite el flujo de mensajes y la coordinación entre una amplia variedad de sistemas de la empresa; comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y sistemas externos se controlan a través de adaptadores que toman mensajes externos y transforman en un formato adecuado para el procesamiento por [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  

 Estas dos tecnologías que forman una intersección en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] del adaptador de WCF. Puede consumir los enlaces expuestos por WCF y consumir, por tanto, las operaciones y los datos expuestos por el adaptador escrito con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  

 Las ilustraciones siguientes se proporciona una descripción general de cómo se utilizan los adaptadores de LOB de WCF y el adaptador de WCF de BizTalk dentro [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para comunicarse con sistemas LOB de destino.  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8dd622c6-ab5e-4cd9-aa86-5176f5c62203.gif "8dd622c6-ab5e-4cd9-aa86-5176f5c62203")  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4f503084-da4f-41cb-92b9-eaea25d1b456.gif "4f503084-da4f-41cb-92b9-eaea25d1b456")  

## <a name="differences-between-the-sdk-and-the-biztalk-server-adapter-framework"></a>Diferencias entre el SDK y el entorno de adaptador de BizTalk Server

Aunque tanto la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador Framework proporcionan un SDK para escribir adaptadores personalizados, aparecen las diferencias significativas en la cantidad de soporte técnico proporcionado en cuanto a la API y herramientas y también en la reutilización del adaptador una vez es puede completar.  

 En la tabla siguiente se resumen algunas de las principales diferencias entre los dos marcos.  


|     Característica      |                                                                   [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]                                                                   |                  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Entorno de adaptador                   |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|       API        | [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] y [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)] ensamblado, proporciona clases de ayuda para los metadatos de procesamiento, administración de conexiones y mensajería |                                            COM, proporciona compatibilidad básica para las operaciones del adaptador.                                             |
| Exposición de adaptador |                                                            Exponer como enlace de WCF; disponible para cualquier aplicación que puede consumir un enlace WCF.                                                             | Expuesto solo a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]; no puede reutilizar en otras aplicaciones. |
|      Herramientas       |                       [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)], el Explorador de metadatos para [!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]                       |                                                                    n/d                                                                     |
|  Extensibilidad   |                                                                                       Sí (como extensión de canal WCF)                                                                                        |                                                                     no                                                                     |

 Los adaptadores creados mediante el adaptador de BizTalk Framework son dese solo dentro de BizTalk Server. Por otro lado, los adaptadores que se escriben en el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se exponen como enlaces WCF personalizados. Esto amplía su alcance a cualquier aplicación que consume un servicio, que en la práctica es cualquier .NET incluidas aplicación [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Los adaptadores de WCF se utilizan dentro de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de WCF de BizTalk y continúan existiendo en paralelo con los adaptadores nativos de BizTalk. 

