---
title: "Cómo consumir matrices de servicios Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- Web services, arrays
- orchestrations, Web services
- orchestrations, Web ports
ms.assetid: 29ecaaed-aa8a-4cf9-a7c8-4b0d6dd412ac
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e78f12405c9c331a888a268d39e2a1520c84fdc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-consume-web-service-arrays"></a>Cómo consumir matrices de servicios Web
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona la capacidad de consumir las matrices expuestas en servicios Web de una orquestación de BizTalk.  
  
 **Para configurar una orquestación para consumir una matriz expuesta en un servicio Web:**  
  
 Determine la URL para el servicio Web que expone las matrices. Ésta corresponde normalmente a una página Web asmx que enumera las operaciones admitidas por el servicio Web. Por ejemplo: http://localhost/ArrayWS/ArraySvc.asmx.  
  
1.  Agregue una referencia Web a esta URL en el proyecto de Visual Studio que contenga su orquestación.  
  
    -   En el Explorador de soluciones, haga clic en **referencias**y haga clic en **Agregar referencia de servicio**.  
  
    -   En el **Agregar referencia de servicio** cuadro de diálogo, haga clic en **avanzadas**.  
  
    -   En el **configuración de referencia de servicio** cuadro de diálogo, haga clic en **Agregar referencia Web** en el **compatibilidad** sección.  
  
    -   En el **Agregar referencia Web** diálogo cuadro, escriba la dirección URL para el servicio Web en el **URL** cuadro de texto y, a continuación, haga clic en **vaya**.  
  
    -   Escriba un nombre para la referencia Web en el **nombre de referencia Web** cuadro de texto y haga clic en el **Agregar referencia** botón.  
  
    -   La referencia Web aparecerá en **referencias Web** en el Explorador de soluciones.  
  
        > [!TIP]
        >  Una vez haya agregado al proyecto una referencia Web la **Agregar referencia Web** comando está directamente disponible cuando hace clic en el nombre del proyecto o **referencias** o **referencias Web**.  
  
2.  Agregar un puerto Web a la orquestación:  
  
    -   Arrastre un **puerto** superficies de forma desde el cuadro de herramientas a uno de los puertos en el Diseñador de orquestaciones para iniciar la **Asistente de configuración de puerto**. Haga clic en el **siguiente** botón en el **Asistente para configuración de puertos** para mostrar la **propiedades de puerto** cuadro de diálogo.  
  
    -   Especifique un valor para el **nombre** cuadro de texto para identificar el puerto y haga clic en el **siguiente** botón para mostrar el **seleccionar un tipo de puerto** cuadro de diálogo.  
  
    -   Seleccione la opción de **utilizar un tipo de puerto existente**, seleccione el puerto Web tipo que corresponde a la Web hacen referencia a que ha agregado y haga clic en el **siguiente** botón para mostrar el **deenlacedepuerto**cuadro de diálogo.  
  
    -   En el **enlace de puerto** cuadro de diálogo Seleccione la **enlace de puerto** opción y haga clic en el **siguiente** , a continuación, haga clic en el **finalizar** botón. Ahora debería tener un puerto Web que se muestra en el Diseñador de orquestaciones que incluya las operaciones admitidas por el servicio Web.  
  
3.  Agregar **enviar** y **recepción** formas a la orquestación según corresponda:  
  
    -   Arrastre un **enviar** forma desde el cuadro de herramientas a una línea de conexión en la superficie del Diseñador de orquestaciones para configurar la orquestación para enviar un mensaje de solicitud al puerto Web. Si se conecta el **enviar** forma a uno del puerto Web de conectores de mensajes de solicitud, BizTalk creará automáticamente un mensaje del tipo adecuado que se utilizará al enviar un mensaje de solicitud a este puerto.  
  
    -   Arrastre un **recepción** forma desde el cuadro de herramientas a una línea de conexión en la superficie del Diseñador de orquestaciones para configurar la orquestación para recibir un mensaje de respuesta del puerto Web. Si se conecta el **recepción** forma a uno de los conectores de mensaje de respuesta de puerto Web, BizTalk creará automáticamente un mensaje del tipo adecuado que se utilizará al recibir un mensaje de respuesta de este puerto.  
  
> [!NOTE]
>  Use el adaptador de SOAP para enviar o recibir mensajes desde un servicio Web. Para obtener más información acerca de cómo configurar el adaptador de SOAP, vea [configurar el adaptador de SOAP](../core/configuring-the-soap-adapter.md).  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] motor de orquestaciones proporciona compatibilidad para consumir una dimensión y escalonadas matrices expuestas por los servicios Web. Si agrega una referencia Web a un servicio Web que exponga matrices, el Diseñador de orquestaciones generará un tipo de mensaje Web que describa la matriz. Puede enviar y recibir mensajes de este tipo de la misma forma que con cualquier otro mensaje. BizTalk Server no limita el envío de mensajes Web que contengan matrices para solo puertos Web.  
  
 Para obtener un ejemplo sobre cómo consumir matrices de servicios Web, vea el ejemplo SDK "Consume Web Services" y "Consume Web Services with Array Parameters" en [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="see-also"></a>Vea también  
 [Usar mensajes en orquestaciones](../core/using-messages-in-orchestrations.md)