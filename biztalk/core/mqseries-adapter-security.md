---
title: Seguridad del adaptador de MQSeries | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, MQSeries adapters
- MQSeries adapters, security
ms.assetid: 0bd82c21-6b77-4a66-a4e9-4a91ba4a56c4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3ef0bf698515d00b60e7ffb8b2124576e9a001
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019521"
---
# <a name="security-with-the-mqseries-adapter"></a>Seguridad con el adaptador de MQSeries

La seguridad del adaptador de MQSeries comienza con la protección de los servidores MQSeries y BizTalk Server. Para obtener información acerca de cómo proteger el servidor BizTalk Server, vea [seguro y proteger los datos](secure-and-protect-your-biztalk-messages.md). Para obtener información acerca de la seguridad del servidor MQSeries, vea la documentación del servidor MQSeries de IBM.  
  
> [!NOTE]
>  El adaptador utiliza automáticamente privacidad de paquete para el envío y la recepción de mensajes entre el servidor BizTalk Server y el servidor MQSeries.  

## <a name="adapter-security"></a>Seguridad del adaptador  
 Para utilizar el adaptador mismo de forma segura, es preciso prestar atención a cuatro áreas:  
  
- La selección de la identidad de la aplicación y los miembros para MQSAgent  
  
- El control de las cuentas de BizTalk Server que utilizan el adaptador  
  
- La protección de las secuencias de comandos de creación de cola  
  
- Uso apropiado de la **aplicación afiliada de SSO** propiedad  
  
  La cuenta asignada a la identidad de la aplicación durante la configuración no debería ser una cuenta de administrador. En su lugar, la cuenta debe tener los privilegios mínimos necesarios, acceso de lectura y escritura a las colas de MQSeries.  
  
  Asegúrese de asignar únicamente cuentas de BizTalk Server que utilizan el adaptador a la función MQSAgent.  
  
  Al utilizar secuencias de comandos exportadas, creadas durante el proceso de definición de cola, mantenga las secuencias de comandos en un área segura. Sólo deberían tener acceso los administradores que utilicen las secuencias de comandos.  
  
  Si la aplicación usa las propiedades de encabezado MQCIH y MQIIH para colocar las credenciales de usuario en los mensajes de salida, use el **aplicación afiliada de SSO** propiedad en el **propiedades de transporte** página. Para obtener más información acerca de esta propiedad, vea [cómo configurar ubicaciones de recepción de MQSeries adaptadores y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).  
  
## <a name="see-also"></a>Vea también  
 [Estructura del adaptador de MQSeries](../core/structure-of-the-mqseries-adapter.md)   
 [¿Qué es el adaptador de MQSeries?](../core/what-is-the-mqseries-adapter.md)