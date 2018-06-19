---
title: Acerca de los mensajes de instancia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de7fc3d3-57a7-4df9-b981-127e21941e22
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf956fb9f201697ac8c2b7da2135e469e03de55e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224780"
---
# <a name="about-instance-messages"></a>Acerca de los mensajes de instancia
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía y recibe mensajes de instancia, cada uno de los cuales representa normalmente uno o varios documentos empresariales, como un pedido de compra. Un mensaje de instancia es una instancia de una estructura de mensaje definida por uno o más esquemas Un esquema, o un conjunto de esquemas utilizados de forma conjunta, define lo que constituye un mensaje de instancia válido. Por ejemplo, se puede establecer que un pedido de compra tenga varios registros dentro; por ejemplo, un registro ShipTo, un registro BillTo, un registro Items, etc. Cada uno de estos registros se puede definir de modo que contenga sus propios subregistros y campos. El esquema correspondiente define el contenido potencial de estos registros y campos, y los mensajes de instancia correspondientes incluyen los pedidos de compra reales que contienen datos de pedidos de compra estructurados en función del esquema.  
  
 BizTalk Server puede enviar y recibir mensajes de instancia en una variedad ampliable de formatos, aunque un formato, XML, tiene una importancia especial como el formato al que se convierten todos los formatos de mensajes para el procesamiento interno. Un documento XML específico utiliza un conjunto definido de etiquetas de inicio y finalización, organizadas de forma jerárquica, para organizar los datos dentro del mensaje y determinar dónde termina una elemento de datos y dónde empieza otro. Uno o más esquemas XML correspondientes definen qué etiquetas se permiten dentro de otras etiquetas, además de en qué orden, con lo que se establece la estructura que rige los mensajes que cumplen las especificaciones.  
  
 Otra amplia categoría de formatos, conocida como formatos de archivo sin formato, la utilizan habitualmente los sistemas heredados. Estos formatos usan una combinación de delimitadores (como caracteres de tabulación) y campos de longitud fija para determinar dónde termina un elemento de datos y dónde empieza otro.  
  
 En esta sección se proporciona información general avanzada sobre la estructura de estos dos tipos de mensajes que utiliza habitualmente BizTalk Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Estructura de un mensaje XML](../core/structure-of-an-xml-message.md)  
  
-   [Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md)