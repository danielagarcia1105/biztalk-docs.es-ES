---
title: 'Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server con el adaptador de Siebel | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41338723-055d-46b4-acee-6969ea79fac0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f779c9b347c43fb9bd2a6dcdbdb3c33ac8ad09c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009133"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-with-the-siebel-adapter"></a>Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server con el adaptador de Siebel
![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realiza las siguientes tareas:  
  
- Crear un WCF-Custom envío-puerto de recepción para enviar y recibir mensajes desde el sistema de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Configurar este puerto para utilizar las asignaciones que creó en el paso anterior.  
  
- Configurar la orquestación ha implementado en el último paso para usar el puerto de WCF-Custom.  
  
## <a name="prerequisite"></a>Requisito previo  
  
-   Debe haber implementado la orquestación de BizTalk para el que desea configurar el puerto de WCF-Custom.  
  
### <a name="to-create-a-wcf-custom-port"></a>Para crear un puerto de WCF-Custom  
  
1. Cuando se genere el esquema para una operación en el sistema de Siebel mediante [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], un archivo de enlace también se agrega al proyecto de BizTalk. Puede importar este archivo de enlace en el BizTalk aplicación para crear un WCF-Custom envío-puerto de recepción. Para obtener instrucciones sobre cómo importar un archivo de enlace, consulte [importar enlaces](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372).  
  
2. Después de importar el archivo de enlace, se crea un puerto de envío en el **puertos de envío** carpeta en la consola de administración de BizTalk Server.  
  
3. Haga clic en el puerto de WCF-Custom y, a continuación, haga clic en **propiedades**.  
  
4. En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en el **General** ficha. En el panel derecho, haga clic en **configurar**.  
  
5. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** pestaña y especifique las credenciales para conectarse a un sistema Siebel.  
  
6. Haga clic en **Aceptar**.  
  
7. En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de entrada**. En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **ResponseMap**.  
  
    ![Configurar asignación de entrada](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")  
  
8. En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de salida**. En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **RequestMap**.  
  
    ![Configurar asignación de salida](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")  
  
9. Haga clic en **Aceptar**.  
  
### <a name="to-configure-the-biztalk-application"></a>Para configurar la aplicación de BizTalk  
  
1. En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda la aplicación de BizTalk donde se implementa la orquestación.  
  
2. Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.  
  
3. En el panel izquierdo, haga clic en el que se va a configurar la orquestación. En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.  
  
4. En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.  
  
   1. Seleccione el puerto de archivo donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarlo al sistema Siebel.  
  
   2. Seleccione el puerto de archivo donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta en el sistema Siebel.  
  
   3. Seleccione el puerto de envío WCF-Custom que creó anteriormente en este tema.  
  
   4. Haga clic en **Aceptar**.  
  
      Para obtener más información acerca de cómo configurar una aplicación, consulte "Cómo configurar una aplicación" en [ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora ha completado la migración de su proyecto de BizTalk vPrev para un proyecto de BizTalk que envía mensajes al sistema Siebel mediante basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Ahora debe probar la aplicación migrada de BizTalk mediante el envío de un mensaje de solicitud para invocar la operación de inserción en el componente empresarial de cuenta, como se describe en [paso 3: probar la aplicación migrado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Migración de proyectos de BizTalk de Siebel](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)