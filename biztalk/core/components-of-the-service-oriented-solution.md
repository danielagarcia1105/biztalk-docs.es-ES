---
title: Solución orientada a servicios de componentes del servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
- service solution tutorial, assemblies
- service solution tutorial, components [BizTalk Server]
- service solution tutorial, client applications
- assemblies, service solutions
- orchestrations, service solutions
- client applications, service solutions
- back-end systems
- service solution tutorial, orchestrations
- service solution tutorial, back-end applications
ms.assetid: 97b7b754-abfb-48f9-87bf-7fe171121166
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 888372550e62e72f21e9d397ac35d17f68c1a187
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017153"
---
# <a name="components-of-the-service-oriented-solution"></a>Solución orientada a servicios de componentes del servicio
En esta sección se describen los principales componentes de BizTalk Server de la solución orientada a servicios. El siguiente diagrama muestra los principales componentes de la solución:  
  
 ![Diagrama de flujo de solución orientada a servicios](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")  
  
 La solución orientada a servicios tiene tres versiones de las orquestaciones:  
  
- Una versión en la que las tres aplicaciones servidor son auxiliares  
  
- Una versión en la que las tres aplicaciones servidor se invocan en línea  
  
- Una versión que utiliza adaptadores para conectarse a las aplicaciones.  
  
  Todas las versiones de las orquestaciones se muestran en el directorio SDK\Senarios\SO\BTSSoln\Orchestrations.  
  
  La versión en línea de las orquestaciones ofrece el tiempo más bajo de latencia entre las solicitudes y las respuestas dentro de la solución.  
  
  Para obtener información acerca de los archivos de origen, vea [inventario de archivos para la solución orientada a servicios](../core/file-inventory-for-the-service-oriented-solution.md).  
  
## <a name="orchestrations-in-the-service-oriented-solution"></a>Orquestaciones en la solución orientada a servicios  
 Las tres orquestaciones, **CustomerServiceReceiveSend**, **CustomerServiceNativeRequestResponse**, y **CustomerService** componen la mayor parte de la solución. El **CustomerServiceReceiveSend** y **CustomerServiceNativeRequestResponse** orquestaciones actúan como servidores front-end que llaman a la **CustomerService** orquestación. El **CustomerService** orquestación realiza la mayor parte del trabajo: envío de solicitudes a las aplicaciones de back-end, recopila las respuestas, combina en un único mensaje y enviar el mensaje correspondientes front-end orquestación. Ya que las orquestaciones cliente llaman a la **CustomerService** las orquestaciones de front-end de orquestación, esperan hasta que el **CustomerService** orquestación finalice.  
  
 La solución expone el **CustomerServiceNativeRequestResponse** orquestaciones como servicios Web. El **CustomerServiceReceiveSend** orquestación toma los mensajes de una cola de MQSeries.  
  
## <a name="back-end-applications"></a>Aplicaciones de servidor  
 La solución orientada a servicios se comunica con tres aplicaciones servidor:  
  
- El **PaymentTracker** aplicación devuelve una lista simulada de pagos recientes. **PaymentTracker** lee la solicitud de una cola de MQSeries y envía la respuesta a otra cola de MQSeries.  
  
- El **PendingTransaction** aplicación informa de la suma de las transacciones pendientes en la cuenta del cliente. La aplicación es un servicio Web que, a su vez, utiliza Microsoft Host Integration Server (HIS) para comunicarse con un programa CICS/COBOL en un gran sistema (mainframe).  
  
- La aplicación SAP suministra información sobre el límite de crédito global del cliente. La solución se conecta a la aplicación SAP como servicio Web. Usa el Conector para SAP en [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para comunicarse con un sistema SAP.  
  
## <a name="pipelines"></a>Canalizaciones  
 La solución orientada a servicios utiliza canalizaciones predeterminadas excepto en dos lugares: la canalización de recepción para el **CustomerServiceReceiveSend** orquestación y el **CustomerService** envío de orquestación canalización para la **PaymentTracker**. Ambas canalizaciones utilizan componentes personalizados.  
  
 La canalización de recepción para **CustomerServiceReceiveSend** incluye un componente de resolución de entidad personalizado, **componente de canalización de emisor de vale de SSO**. Los mensajes que el **CustomerServiceReceiveSend** recibe la orquestación no disponga de credenciales. Esto simula lo que ocurriría si los mensajes procediesen de un sistema de respuesta interactiva de voz. El componente de canalización personalizado agrega credenciales mediante la cuenta de servicio del host de recepción de BizTalk.  
  
 En cambio, los mensajes de la **Customerservicenativerequestresponse** orquestación recibe ya tienen credenciales. Puesto que la carpeta virtual para el servicio Web está configurada para seguridad integrada y la ubicación de recepción de SOAP está configurada para integrar el inicio de sesión único (SSO) empresarial, el adaptador de SOAP genera un vale para el mensaje.  
  
 La otra canalización personalizada aparece en la **CustomerService** canalización de envío para el **PaymentTracker** aplicación. El Componente de canalización establecedor de encabezado de MQSeries establece los valores para dos propiedades de encabezado de mensaje de MQSeries. El componente establece la primera, el formato de datos del mensaje (**MQMD_Format**) para indicar que el mensaje está en forma de un **MQCIH** estructura, una estructura utilizada habitualmente para comunicarse con los programas CICS. El segundo, el formato de los propios datos dentro de la **MQCIH** estructura (**MQCIH_Format**), se establece para mostrar el mensaje es una cadena.  
  
 Mediante el **MQCIH** formato le permite pasar el Id. de usuario y contraseña en el **MQCIH** estructura. Aplicaciones afiliadas de SSO asignan Id. de usuario de Windows de la aplicación de BizTalk para Id el pago del sistema de seguimiento pasado en el **MQCIH** estructura.  
  
> [!NOTE]
>  La versión en línea de la solución utiliza las mismas canalizaciones al llamarlas desde la orquestación. Esto permite reutilizar el código de canalización.  
  
## <a name="client-application"></a>Aplicación de cliente  
 La solución incluye una aplicación cliente escrita en C#. Puede utilizarla para enviar solicitudes en forma de mensajes de SOAP o MQSeries y examinar los resultados  
  
## <a name="other-assemblies"></a>Otros ensamblados  
 La aplicación incorpora varios ensamblados auxiliares que no se muestran en el diagrama de resumen anterior. El **utilidades** funciones de utilidad de ensamblado para la solución.  
  
 El **ErrorHelper** ensamblado contiene clases para traducir los códigos de error en los mensajes y para convertir los mensajes de error a códigos de error.  
  
 El **ServiceLevelTracking** ensamblado incluye métodos auxiliares que utilizan Business Activity Monitoring (BAM) API para realizar un seguimiento de los datos del acuerdo de nivel de servicio.  
  
 El **ConfigHelper** ensamblado contiene métodos auxiliares para recuperar valores de configuración de la solución desde la **SSOConfigStore** aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de un servicio de la solución orientada a servicios](../core/developing-a-service-oriented-solution.md)   
 [Inventario de archivos para la solución orientada a servicios](../core/file-inventory-for-the-service-oriented-solution.md)