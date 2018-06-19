---
title: Recibir IDOC de SAP en un contexto transaccional usando el servidor BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactional context
- IDOCs, receiving in a transactional context using BizTalk Server
ms.assetid: 6a01bb82-7292-4b70-8ad7-996d389a9365
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8903b6010555b3c7c6aba9a07e12c9204bcf19c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962746"
---
# <a name="receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server"></a>Recibir IDOC de SAP en un contexto transaccional usando el servidor BizTalk Server
Recibir IDOC en un contexto transaccional es similar a la recepción de tRFCs en un contexto transaccional. En tal caso, el IDOC recibido desde el sistema SAP contiene un TID como parte de la  *\<TransactionalRfcOperationIdentifier\>*  elemento. Este TID se conserva en una base de datos SQL por el adaptador. Si el código ABAP en el sistema SAP que envía el IDOC tiene una instrucción "COMMIT WORK", se elimina el TID de la base de datos SQL después de una respuesta se envía al sistema SAP.  
  
 La orquestación necesita para recibir un IDOC es similar con independencia de si se recibe el IDOC en un contexto transaccional o no. Vea [recibir IDOC desde SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md). Sin embargo, debe realizar ciertas tareas adicionales para asegurarse de que se recibe lo IDOC en un contexto transaccional.  
  
1.  En tiempo de diseño, generar el esquema para un IDOC que desea recibir.  
  
2.  En tiempo de ejecución, asegúrese de establecer la propiedad de enlace **TidDatabaseConnectionString**. Esta propiedad toma la cadena de conexión para conectarse a una base de datos SQL para almacenar el TID. Una cadena de conexión de ejemplo sería:  
  
    ```  
    Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
    ```  
  
     Para obtener más información acerca de la propiedad de enlace y cómo configurarlo, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
    > [!IMPORTANT]
    >  El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para instalación instala una instancia de SQL en el script, SapAdapter-DbScript-Install.sql, que se debe ejecutar el Administrador de SQL Server para crear una base de datos y los objetos de base de datos en SQL Server. La secuencia de comandos se instala normalmente en  *\<unidad de instalación\>*: programa FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
    >   
    >  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza estos objetos para conservar el TID. Por lo tanto, el Administrador de SQL Server debe asegurarse de que el nombre de usuario proporcionar como parte de la cadena de conexión tiene privilegios suficientes para ejecutar los procedimientos almacenados. También puede optar por la autenticación de Windows siempre que el usuario de Windows tenga permisos suficientes para ejecutar procedimientos almacenados en la base de datos.  
  
3.  Asegúrese de que MSDTC está habilitado en el equipo donde está instalado el adaptador. Realice los pasos siguientes para habilitar MSDTC.  
  
    1.  Inicie el complemento de MMC Servicios de componentes.  
  
    2.  En el complemento MMC Servicios de componentes, en el panel izquierdo expanda **servicios de componentes**, expanda **equipos**, haga clic en **Mi PC**y haga clic en  **Propiedades**.  
  
    3.  En el **propiedades de Mi PC** cuadro de diálogo, haga clic en el **MSDTC** ficha.  
  
    4.  En el **configuración de transacción** sección, haga clic en el **configuración de seguridad** botón.  
  
    5.  En el **configuración de seguridad** cuadro de diálogo, seleccione la **acceso de red DTC** casilla de verificación y dentro de ella, seleccione la **Permitir clientes remotos** casilla de verificación.  
  
    6.  En el **comunicación con el Administrador de transacciones** sección, seleccione la **Permitir entrantes** y **Permitir salientes** casillas de verificación.  
  
    7.  En el **configuración de seguridad** cuadro de diálogo, haga clic en **Aceptar**.  
  
    8.  Haga clic en **Sí** en el cuadro de diálogo que le informa que se reiniciará el servicio MSDTC. Una vez reiniciado el servicio MSDTC, haga clic en **Aceptar** en el cuadro de diálogo.  
  
    9. En el **propiedades de Mi PC** cuadro de diálogo, haga clic en **Aceptar**.  
  
4.  Agregar MSDTC a la lista de excepciones de Firewall de Windows, si todavía no ha agregado. Ejecute el siguiente comando.  
  
    ```  
    netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
    ```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)