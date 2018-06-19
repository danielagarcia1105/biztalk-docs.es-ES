---
title: Cómo funciona el ejemplo de resolución dinámica | Documentos de Microsoft
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
ms.openlocfilehash: fe7d7b473482c432c8e3ae9ca48cab414a9e9573
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22294892"
---
# <a name="how-the-dynamic-resolution-sample-works"></a>Cómo funciona el ejemplo de resolución dinámica
El ejemplo de resolución dinámica utiliza el componente de canalización de desensamblador de distribuidor de ESB para todos los ejemplos de mensajes que se describe en la sección anterior.  
  
 Para escenarios de mensajería unidireccionales, en el ejemplo se resuelve el extremo utilizando el BRE, IP estática o resolución de XPATH y establece el protocolo de archivo al archivo, FTP o MQSeries.  
  
 Para escenarios de mensajería bidireccionales, el ejemplo resuelve el extremo utilizando la IP estática, BRE, UDDI o resolución de XPATH y establece el protocolo de SOAP en SOAP o WCF-BasicHttp. Además, los ejemplos de resolverán y ejecutan mediante el solucionador BRE, que usa los hechos contenidos en las propiedades de contexto de mensaje y el cuerpo del mensaje para determinar el resultado de la resolución de asignaciones de BizTalk de Microsoft.  
  
 El resultado del proceso de resolución es que todos los ejemplos bidireccionales envía su mensaje a ESB. Servicio de CanadianServices Web situado en http://localhost/ESB.CanadianServices/SubmitPOService.asmx. Además, según el resultado de la resolución, el ejemplo ejecuta el **submitOrder** o **submitPurchase** acción. Además, el componente de canalización de desensamblador de distribuidor de ESB ejecuta dinámicamente una asignación de BizTalk, función especificado o la acción resuelta.  
  
 La figura 1 muestra la que ubicación de recepción de las canalizaciones configuradas para el DynamicResolutionReqResp_SOAP.  
  
 ![Canalizaciones de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")  
  
 **Figura 1**  
  
 **Las canalizaciones configuradas de la DynamicResolutionReqResp_SOAP ubicación de recepción de la aplicación de ejemplo de resolución dinámica**  
  
 Figura 2 muestra las propiedades de cada instancia del componente ESBReceiveXML que utiliza el Desensamblador de distribuidor de ESB.  
  
 ![XML de recepción de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")  
  
 **Figura 2**  
  
 **Las propiedades de cada instancia de los componentes de la canalización de ESBReceiveXML de la aplicación de ejemplo de resolución dinámica**  
  
 Las siguientes propiedades se muestran en la figura 2:  
  
-   **Enabled**. Esta propiedad determina si la canalización está activa. Si se establece en **False**, mensajes atraviesan sin procesar.  
  
-   **Endpoint**. Esta propiedad es la cadena de conexión utilizada para determinar qué resolución que se debe cargar y especifica la configuración del extremo.  
  
-   **Nombredemapa**. Esta propiedad es la cadena de conexión que se usa para determinar qué resolución que se debe cargar y qué asignación de BizTalk a ejecutar. Puede ser el nombre completo de un mapa en lugar de una cadena de conexión de resolución.  
  
-   **Validate**. Cuando se establece en **True** (valor predeterminado), el Desensamblador de distribuidor de ESB componente indica al servicio de transformación de ESB para validar el mensaje de origen con respecto al esquema de origen definido en el mapa se resuelva y ejecutar.  
  
 La figura 3 muestra las propiedades de cada instancia del componente ESBSendPassthrough que usa el distribuidor de ESB.  
  
 ![Resolución dinámica enviar Passthrough](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")  
  
 **Figura 3**  
  
 **Las propiedades de cada instancia de los componentes de la canalización de ESBSendPassthrough de la aplicación de ejemplo de resolución dinámica**  
  
 Las siguientes propiedades se muestran en la figura 3:  
  
-   **Enabled**. Esta propiedad determina si la canalización está activa. Si se establece en **False**, mensajes atraviesan sin procesar.  
  
-   **Endpoint**. Esta propiedad es la cadena de conexión utilizada para determinar a qué resolución se cargue y la configuración de extremo.  
  
-   **Nombredemapa**. Esta propiedad es la cadena de conexión que se usa para determinar qué resolución que se debe cargar y qué asignación de BizTalk a ejecutar. Un nombre completo de un mapa puede usarse en lugar de la cadena de conexión de una resolución.  
  
-   **Validate**. Cuando se establece en **True** (valor predeterminado), el Desensamblador de distribuidor de ESB componente indica al servicio de transformación de ESB para validar el mensaje de origen con respecto al esquema de origen definido en el mapa se resuelva y ejecutar.