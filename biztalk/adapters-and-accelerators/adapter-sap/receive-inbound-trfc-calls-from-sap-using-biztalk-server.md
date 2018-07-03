---
title: Recibir llamadas de tRFC de entrada de SAP con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving using BizTalk Server
- tRFCs, sample
ms.assetid: 500eedea-3d27-478c-a64c-903a1fa2b02f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d83d8710b36d0900c2d7b3a6b02c7d0a389ba4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978621"
---
# <a name="receive-inbound-trfc-calls-from-sap-using-biztalk-server"></a>Recibir llamadas de tRFC de entrada de SAP con BizTalk Server
Una llamada al servidor de tRFC es una llamada de servidor RFC transaccional. La orquestación necesita para recibir una solicitud de cambio en un contexto transaccional es similar a la orquestación para recibir cualquier otro RFC de entrada enviado desde un sistema SAP. Sin embargo, deberá realizar ciertas tareas adicionales para asegurarse de que se reciben los RFC en un contexto transaccional. Para obtener más información acerca de la recepción de una solicitud de cambio entrante desde el sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [recibir llamadas entrantes de RFC de SAP mediante el uso de BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md). Para obtener más información acerca de cómo los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite la recepción de llamadas de tRFC de entrada desde un sistema SAP, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
 Recibir un tRFC de entrada enviado desde un sistema SAP es similar a la recepción de una solicitud de cambio entrante con las siguientes diferencias:  
  
1. En tiempo de diseño, al generar el esquema, asegúrese de seleccionar el tRFC desde el **TRFC** nodo.  
  
2. En tiempo de ejecución, asegúrese de establecer la propiedad de enlace **TidDatabaseConnectionString**. Esta propiedad toma la cadena de conexión para conectarse a una base de datos SQL para almacenar el TID. Una cadena de conexión de ejemplo sería:  
  
   ```  
   Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
   ```  
  
    Para obtener más información acerca de la propiedad de enlace y cómo configurarlo, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
   > [!IMPORTANT]
   >  El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para instalación instala una instancia de SQL script SapAdapter-DbScript-Install.sql, que se debe ejecutar el Administrador de SQL Server para crear una base de datos y los objetos de base de datos en SQL Server. El script se instala normalmente en *\<unidad de instalación\>: programa FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]*.  
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
  
> [!IMPORTANT]
>  Una llamada de tRFC de entrada se usa al recibir los IDOC desde el sistema SAP en un contexto "transaccional".  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)