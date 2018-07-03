---
title: SendMail | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- SMTP adapters
ms.assetid: a0258619-b195-4c8a-8326-77add6e6f04d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2b9f3be3fd54d34cec1bdfadda723a42f3b6c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005685"
---
# <a name="sendmail"></a>SendMail
El ejemplo SendMail muestra el modo en que puede usar el adaptador del Protocolo simple de transferencia de correo (SMTP) para enviar mensajes de correo electrónico dentro de una orquestación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La información dinámica empleada para enviar los mensajes de correo se recupera de un mensaje XML mediante la funcionalidad de promoción de propiedades.  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo envía un mensaje de correo electrónico usando información obtenida de las propiedades promocionadas de un mensaje de pedido (PO) XML entrante, mediante la siguiente secuencia de pasos:  

1. La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera un mensaje de PO XML de entrada.  

2. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orquestación promociona el **PONumber** y **correo electrónico** propiedades para facilitar el acceso en el futuro.  

3. La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa los valores de las propiedades promocionadas para establecer la dirección de destino del puerto de envío dinámico y para establecer el asunto del mensaje de correo electrónico.  

4. La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía el mensaje de correo electrónico construido mediante el adaptador SMTP.  

## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\SendMail\  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  


|                    Archivos                     |                                                                                                         Descripción                                                                                                         |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AssemblyInfo.cs, SendMail.btproj, SendMail.sln |                                                                         Proporciona archivos de información de proyectos, soluciones y ensamblados para este ejemplo.                                                                         |
|                  Cleanup.bat                   |              Anula la implementación de ensamblados y los elimina de la caché de ensamblados global (GAC); elimina puertos de envío y de recepción; elimina directorios virtuales de los Servicios de Microsoft Internet Information Server (IIS) según sea necesario.               |
|     PropertySchema.xsd, PurchaseOrder.xsd      |                                                           Proporciona esquemas para las propiedades que se desea promocionar y para el mensaje de PO XML, respectivamente.                                                           |
|                ReceiveSend.odx                 |   Proporciona una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que procesa el mensaje de PO XML entrante y envía un mensaje de correo electrónico basado en la información del mensaje.   |
|               SendMailInput.xml                |                                                                                 Contiene un archivo de entrada de ejemplo con un PO especificado mediante XML.                                                                                 |
|                   Setup.bat                    | Crea e inicializa este ejemplo. **Nota:** este archivo de instalación crea y enlaza puertos, y así sucesivamente, utilizando un mecanismo diferente que la mayoría de la configuración de los archivos de los ejemplos del SDK. No requiere ningún archivo .xml complementario. |

### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  

1. En una ventana de comandos, desplácese a la siguiente carpeta:  

    \<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\SendMail  

2. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  

   - Crea la siguiente carpeta de entrada para este ejemplo:  

      \<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\SendMail\In  

   - Compila el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  

   - Inicia la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

     > [!NOTE]
     >  Debe confirmar que BizTalk no ha informado de ningún error durante el proceso de generación e inicialización antes de intentar ejecutar este ejemplo.  

     > [!NOTE]
     >  Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la Utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar el ensamblado resultante.  

     > [!NOTE]
     >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat y elimine todos los puertos de recepción y envío que tengan el prefijo SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  

3. En el **administración de BizTalk Server** de consola, busque el puerto de recepción prefijado por SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail. Actualice la ubicación de recepción para que este puerto de recepción señale a un directorio del sistema de archivos para su uso como ubicación de entrada.  

4. Con un programa como el Bloc de notas, modifique el archivo SendMailInput.xml para que el **correo electrónico** elemento especifica una dirección de correo electrónico a la que desea recibir el mensaje de correo electrónico generado por este ejemplo.  

5. Haga clic en **iniciar**, apunte a **programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

6. En el **administración de BizTalk Server** de consola, expanda el árbol de grupo de BizTalk.  

7. Expanda el **configuración de plataforma** árbol en el panel izquierdo.  

8. Expanda el **adaptadores** carpeta, haga clic en el **SMTP** nodo y, a continuación, haga doble clic en el adaptador de SMTP de fila en el panel derecho.  

9. En el **SMTP - propiedades de controlador de adaptador** cuadro de diálogo, haga clic en **propiedades**.  

10. En el **propiedades de transporte SMTP** cuadro de diálogo el **propiedades** pestaña, proporcione los valores adecuados para el **nombre del servidor SMTP** y **desde (correo electrónico dirección)** propiedades y, a continuación, haga clic en **Aceptar**.  

     Estos valores se usarán para construir la dirección de correo electrónico De para cualquier mensaje de correo electrónico enviado a través de este adaptador de SMTP.  

    > [!NOTE]
    >  Si tiene que autenticarse con el servidor SMTP, debe asegurarse de que la dirección de correo electrónico De pertenezca a la misma cuenta que usa para la autenticación.  

11. Detenga el servicio de BizTalk y después reinícielo (BizTalkServerApplication) para que la orquestación adopte estos cambios.  

### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  

1.  Coloque una copia del archivo SendMailInput.xml modificado en la carpeta de entrada.  

2.  Observe si llega un mensaje de correo electrónico a la dirección especificada en el procedimiento anterior.  

## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores: uso](../core/adapter-samples-usage.md)