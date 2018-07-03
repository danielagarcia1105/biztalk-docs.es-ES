---
title: Cómo funciona el ejemplo de resolución dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bab7a46a02dc080fa27b9df2b30614bc8a45c6e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976437"
---
# <a name="how-the-dynamic-resolution-sample-works"></a>Cómo funciona el ejemplo de resolución dinámica
El ejemplo de resolución dinámica utiliza el componente de canalización de desensamblador de distribuidor de ESB para todos los ejemplos de mensajes que se describe en la sección anterior.  

 Para escenarios de mensajería unidireccionales, en el ejemplo se resuelve como el punto de conexión mediante la estática, el BRE o resolución de XPATH y negocia el protocolo de archivo para el archivo, FTP o MQSeries.  

 Para escenarios de mensajería bidireccionales, el ejemplo se resuelve como el punto de conexión mediante estático, BRE, UDDI o resolución de XPATH y negocia el protocolo de SOAP en SOAP o WCF-BasicHttp. Además, los ejemplos de resolverán y ejecutan mediante la resolución del BRE, que usa los datos contenidos en las propiedades de contexto de mensaje y el cuerpo del mensaje para determinar el resultado de la resolución de asignaciones de BizTalk de Microsoft.  

 El resultado del proceso de resolución es que todos los ejemplos bidireccionales enviar su mensaje a ESB. Servicio CanadianServices Web ubicado en http://localhost/ESB.CanadianServices/SubmitPOService.asmx. Además, según el resultado de la resolución, el ejemplo ejecuta el **submitOrder** o **submitPurchase** acción. Además, el componente de canalización de desensamblador de distribuidor de ESB ejecuta dinámicamente según especificado o la acción resolver una asignación de BizTalk.  

 Figura 1 muestra la que ubicación de recepción de las canalizaciones configuradas para el DynamicResolutionReqResp_SOAP.  

 ![Canalizaciones de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")  

 **Figura 1**  

 **Las canalizaciones configuradas de la DynamicResolutionReqResp_SOAP recepción la ubicación de la aplicación de ejemplo de resolución dinámica**  

 Figura 2 muestra las propiedades de cada instancia del componente ESBReceiveXML que utiliza el Desensamblador de distribuidor de ESB.  

 ![XML de recepción de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")  

 **Figura 2**  

 **Las propiedades de cada instancia de los componentes de la canalización ESBReceiveXML de la aplicación de ejemplo de resolución dinámica**  

 Las siguientes propiedades se muestran en la figura 2:  

- **Habilitado**. Esta propiedad determina si la canalización está activa. Si se establece en **False**, los mensajes pasan a través sin procesamiento.  

- **Punto de conexión**. Esta propiedad es la cadena de conexión utilizada para determinar qué resolución para cargar y especifica la configuración de punto de conexión.  

- **Nombredemapa**. Esta propiedad es la cadena de conexión que se usa para determinar qué resolución para cargar y qué asignación de BizTalk a ejecutar. Puede ser el nombre completo de un mapa en lugar de una cadena de conexión de la resolución.  

- **Validar**. Cuando se establece en **True** (valor predeterminado), el Desensamblador de distribuidor de ESB componente indica al servicio de transformación de ESB para validar el mensaje de origen con respecto al esquema de origen definido en la asignación que se va resolver y la ejecutará.  

  Figura 3 muestra las propiedades de cada instancia del componente ESBSendPassthrough que utiliza el distribuidor de ESB.  

  ![Paso a través de envío de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")  

  **Figura 3**  

  **Las propiedades de cada instancia de los componentes de la canalización ESBSendPassthrough de la aplicación de ejemplo de resolución dinámica**  

  Las siguientes propiedades se muestran en la figura 3:  

- **Habilitado**. Esta propiedad determina si la canalización está activa. Si se establece en **False**, los mensajes pasan a través sin procesamiento.  

- **Punto de conexión**. Esta propiedad es la cadena de conexión utilizada para determinar a qué resolución para carga y la configuración de punto de conexión.  

- **Nombredemapa**. Esta propiedad es la cadena de conexión que se usa para determinar qué resolución para cargar y qué asignación de BizTalk a ejecutar. Un nombre completo de un mapa puede usarse en lugar de la cadena de conexión de una resolución.  

- **Validar**. Cuando se establece en **True** (valor predeterminado), el Desensamblador de distribuidor de ESB componente indica al servicio de transformación de ESB para validar el mensaje de origen con respecto al esquema de origen definido en la asignación que se va resolver y la ejecutará.
