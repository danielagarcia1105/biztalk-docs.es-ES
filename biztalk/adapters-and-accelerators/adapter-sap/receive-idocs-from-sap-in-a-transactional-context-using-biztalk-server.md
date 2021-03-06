---
title: Recibir los IDOC desde SAP en un contexto transaccional usando el servidor BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: c58bccbb48603af8bf5a5cc0d12b4c2200e78704
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013367"
---
# <a name="receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server"></a>Recibir los IDOC desde SAP en un contexto transaccional usando el servidor BizTalk Server
Recibir IDOC en un contexto transaccional es similar a la recepción de trfc en un contexto transaccional. En tal caso, el IDOC recibido desde el sistema SAP contiene un TID como parte de la *\<TransactionalRfcOperationIdentifier\>* elemento. Este TID se conserva en una base de datos SQL por el adaptador. Si el código ABAP en el sistema SAP que envía el IDOC tiene una instrucción "COMMIT WORK", se elimina el TID desde la base de datos SQL después de que se envía una respuesta al sistema SAP.  
  
 La orquestación necesita para recibir un IDOC es similar, independientemente de si se recibe el IDOC en un contexto transaccional o no. Consulte [recibir los IDOC desde SAP utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md). Sin embargo, deberá realizar ciertas tareas adicionales para asegurarse de que se recibe lo IDOC en un contexto transaccional.  
  
1. En tiempo de diseño, generar el esquema para un IDOC que desee recibir.  
  
2. En tiempo de ejecución, asegúrese de establecer la propiedad de enlace **TidDatabaseConnectionString**. Esta propiedad toma la cadena de conexión para conectarse a una base de datos SQL para almacenar el TID. Una cadena de conexión de ejemplo sería:  
  
   ```  
   Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
   ```  
  
    Para obtener más información acerca de la propiedad de enlace y cómo configurarlo, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
   > [!IMPORTANT]
   >  El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para instalación instala una instancia de SQL script SapAdapter-DbScript-Install.sql, que se debe ejecutar el Administrador de SQL Server para crear una base de datos y los objetos de base de datos en SQL Server. El script se instala normalmente en  *\<unidad de instalación\>*: programa FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
   > 
   >  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza estos objetos para conservar el TID. Por lo tanto, el Administrador de SQL Server debe asegurarse de que el nombre de usuario proporcionan como parte de la cadena de conexión tiene privilegios suficientes para ejecutar los procedimientos almacenados. También puede optar por la autenticación de Windows siempre que el usuario de Windows tiene permisos suficientes para ejecutar procedimientos almacenados en la base de datos.  
  
3. Asegúrese de que MSDTC está habilitada en el equipo donde está instalado el adaptador. Realice los pasos siguientes para habilitar MSDTC.  
  
   1.  Inicie el complemento MMC Servicios de componentes.  
  
   2.  En el complemento MMC Servicios de componentes, en el panel izquierdo expanda **servicios de componentes**, expanda **equipos**, haga clic en **Mi PC**y haga clic en  **Propiedades**.  
  
   3.  En el **propiedades de Mi PC** cuadro de diálogo, haga clic en el **MSDTC** ficha.  
  
   4.  En el **configuración de la transacción** sección, haga clic en el **configuración de seguridad** botón.  
  
   5.  En el **configuración de seguridad** cuadro de diálogo, seleccione el **acceso de red DTC** casilla de verificación y dentro de ella, seleccione el **Permitir clientes remotos** casilla de verificación.  
  
   6.  En el **comunicación del Administrador de transacciones** sección, seleccione el **Permitir entrantes** y **Permitir salientes** casillas de verificación.  
  
   7.  En el **configuración de seguridad** cuadro de diálogo, haga clic en **Aceptar**.  
  
   8.  Haga clic en **Sí** en el cuadro de diálogo que le informa que se reiniciará el servicio MSDTC. Después de reinicia el servicio MSDTC, haga clic en **Aceptar** en el cuadro de diálogo.  
  
   9. En el **propiedades de Mi PC** cuadro de diálogo, haga clic en **Aceptar**.  
  
4. Agregar MSDTC a la lista de excepciones de Firewall de Windows, si no ha agregado. Ejecute el siguiente comando:  
  
   ```  
   netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
   ```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)