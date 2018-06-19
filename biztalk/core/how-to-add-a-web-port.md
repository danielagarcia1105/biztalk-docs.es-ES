---
title: Cómo agregar un puerto Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web ports, creating
- creating, Web ports
ms.assetid: da94d98e-10ca-437a-ba34-7aa6efc68f3d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e9853755788aa29d3ca7506829dcd6bdfed53d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248012"
---
# <a name="how-to-add-a-web-port"></a>Cómo agregar un puerto Web
Los puertos Web se agregan en la superficie para el puerto en el Diseñador de orquestaciones. A diferencia de otros puertos configurados, los puertos Web admiten una mezcla de operaciones de solicitud (unidireccionales) y de solicitud-respuesta (bidireccionales). Cada operación del puerto Web representa un método Web. Si el método Web contiene *entrada* y *salida* parámetros, BizTalk crea una operación de solicitud/respuesta. Si el servicio Web contiene sólo un *entrada* parámetro, BizTalk sólo crea una operación unidireccional.  
  
### <a name="to-add-a-web-port"></a>Para agregar un puerto Web  
  
1.  En el Diseñador de orquestaciones, con una orquestación abierta, haga clic en la superficie del puerto y, a continuación, seleccione **nuevo puerto configurado**.  
  
2.  En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.  
  
3.  En el **propiedades de puerto** página, en la **nombre** cuadro de texto, escriba un nombre para el puerto y, a continuación, haga clic en **siguiente**.  
  
4.  En el **seleccionar un tipo de puerto** , seleccione **utilizar un tipo de puerto existente**.  
  
5.  En el **tipos de puertos disponibles** , expanda la **tipos de puertos Web** nodo y seleccione la Web tipo que se corresponde con el servicio Web agregado de puerto y, a continuación, haga clic en **siguiente**.  
  
     La siguiente ilustración muestra la **seleccionar un tipo de puerto** cuadro de diálogo.  
  
     ![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")  
  
6.  En el **enlace de puerto** página, en la **enlace de puerto** lista desplegable, seleccione **especificar ahora**. BizTalk coloca automáticamente los valores desde el servicio Web al que se hace referencia en el URI, el transporte y las canalizaciones de recepción y envío. BizTalk utiliza estos valores para crear el puerto de envío al implementar el proyecto de BizTalk.  
  
    > [!IMPORTANT]
    >  El método de autenticación predeterminado para el puerto de envío es el acceso anónimo. Si el servicio Web necesita un método de autenticación o de cifrado diferente, debe cambiar la configuración para proporcionar las credenciales de usuario adecuadas o Capa de sockets seguros (SSL) para ejecutar servicios Web. Para obtener más información, consulte [: adaptador de envío SOAP](../core/soap-send-adapter.md) y [TMA de ejemplo: adaptadores SOAP y HTTP](../core/sample-tma-http-and-soap-adapters.md).  
  
7.  Haga clic en **siguiente**y, a continuación, **finalizar** para completar el asistente.  
  
## <a name="see-also"></a>Vea también  
 [Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md)   
 [Creación de puertos Web](../core/creating-web-ports.md)