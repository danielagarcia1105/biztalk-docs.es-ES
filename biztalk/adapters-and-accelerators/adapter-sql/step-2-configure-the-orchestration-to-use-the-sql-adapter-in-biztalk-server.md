---
title: 'Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server mediante el adaptador de SQL | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6152560-5ff0-4bdc-818c-e906b9642f52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6293758d9891d86e137d07e9735ce37162d6a96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984029"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-using-the-sql-adapter"></a>Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server mediante el adaptador de SQL
![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realiza las siguientes tareas:  
  
- Crear un WCF-Custom envío y recepción de puerto para enviar y recibir mensajes de la base de datos de SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Configurar este puerto para utilizar las asignaciones que creó en el paso anterior.  
  
- Configurar la orquestación ha implementado en el paso anterior para usar el puerto de WCF-Custom.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber implementado la orquestación de BizTalk para el que desea configurar el puerto de WCF-Custom, como se describe en [paso 1: modificar el proyecto vPrev de BizTalk mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md).  
  
### <a name="to-create-a-wcf-custom-port"></a>Para crear un puerto de WCF-Custom  
  
1. Cuando se genere el esquema para una operación en la base de datos de SQL Server mediante [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], un archivo de enlace también se agrega al proyecto de BizTalk. Puede importar este archivo de enlace en el BizTalk aplicación para crear un WCF-Custom envío-puerto de recepción. Para obtener instrucciones sobre cómo importar un archivo de enlace, consulte [importar enlaces](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53).  
  
2. Después de importar el archivo de enlace, se crea un puerto de envío en el **puertos de envío** carpeta en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
3. Haga clic en el puerto de WCF-Custom y, a continuación, haga clic en **propiedades**.  
  
4. En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en el **General** ficha. En el panel derecho, haga clic en **configurar**.  
  
5. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha, especifique las credenciales para conectarse a una base de datos de SQL Server y, a continuación, haga clic en **Aceptar**.  
  
6. En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de entrada**. En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **ResponseMap**.  
  
    ![Configurar asignación de entrada](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")  
  
7. En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de salida**. En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **RequestMap**.  
  
    ![Configurar asignación de salida](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")  
  
8. Haga clic en **Aceptar**.  
  
### <a name="to-configure-the-biztalk-application"></a>Para configurar la aplicación de BizTalk  
  
1. En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación de BizTalk donde se implementa la orquestación.  
  
2. Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.  
  
3. En el panel izquierdo, haga clic en el que se va a configurar la orquestación. En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.  
  
4. En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
   1.  Seleccione el puerto de archivo donde se colocará un mensaje de solicitud. La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de SQL Server.  
  
   2.  Seleccione el puerto de archivo donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de SQL Server.  
  
   3.  Seleccione el puerto de envío WCF-Custom que creó anteriormente en este tema.  
  
   4.  Haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora ha completado la migración de su proyecto de BizTalk vPrev para un proyecto de BizTalk que envía mensajes a la base de datos de SQL Server con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Ahora debe probar la aplicación migrada de BizTalk mediante el envío de un mensaje de solicitud para realizar una operación de inserción en la base de datos de SQL Server, como se describe en [paso 3: probar la aplicación migrados que usa el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Migrar proyectos de BizTalk para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)