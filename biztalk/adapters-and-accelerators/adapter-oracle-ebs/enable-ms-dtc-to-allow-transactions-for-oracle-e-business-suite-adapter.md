---
title: Habilitar el Coordinador de transacciones distribuidas de MS permitir que las transacciones de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53037e9a7dc1ccc3c0ef21860696060ad1c046a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984997"
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a>Habilitar el Coordinador de transacciones distribuidas de MS permitir que las transacciones de Oracle E-Business Suite
Configurar MSDTC antes de empezar a crear aplicaciones que usan el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
Las operaciones se realizan sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el modelo de servicio WCF o el modelo de canal WCF) se pueden realizar en un ámbito de transacción. Si el programa cliente tiene más de un recurso transaccional como parte de la misma transacción, la transacción obtiene elevada a una transacción MSDTC. Para habilitar el adaptador realizar operaciones dentro del ámbito de una transacción MSDTC, configure MSDTC del equipo que ejecuta el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]y en Oracle E-Business Suite. También, agregar MSDTC a la lista de excepciones en el firewall, lo que puede ser el Firewall de Windows integrada. 
  
> [!NOTE]
>  Los pasos para configurar MSDTC varían para diferentes sistemas operativos. Los pasos indicados en este tema se aplican al cliente de Windows y sistemas operativos Windows Server.  
  
## <a name="configure-msdtc"></a>Configurar MSDTC  
  
1. Abra **servicios de componentes**.  

   O bien, en **administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **servicios de componentes**.  
  
2. Expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, expanda **Coordinador de transacciones distribuidas**, Haga clic en **DTC Local**y seleccione **propiedades**.  
  
3. Seleccione la pestaña **Seguridad** . En esta pestaña, seleccione todos los elementos siguientes: 

   - **Acceso a DTC desde la red**
   - **Permitir a clientes remotos** 
   - **Permitir entrantes** 
   - **Permitir salientes** 
   - **No hay Authetnication necesario**
  
4. Seleccione **Aceptar** para guardar los cambios.  
  
5. Si se le pide que reinicie el servicio MSDTC, seleccione **Sí**. Después de reinicia el servicio MSDTC, cierre las propiedades y los servicios de componentes de MMC. 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>Agregar MSDTC a la lista de excepciones de Firewall de Windows  

> [!TIP] 
>  Coordinador de transacción distribuida de Microsoft (MSDTC) puede que ya se permitidas en el firewall. Si es así, aparece como una regla de entrada. Si no aparece, use esta sección para permitir MSDTC. 

1.  Abra **Windows Firewall**y seleccione **configuración avanzada** a la izquierda.  

    O bien, en **administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **Firewall de Windows con seguridad avanzada**.  
  
2.  Haga clic en **reglas de entrada**y seleccione **nueva regla**.  
  
3.  En el asistente: 

    1. Seleccione **programa**y seleccione **siguiente**. 
    2. Establecer el **ruta del programa** a `%SystemRoot%\system32\msdtc.exe`y seleccione **siguiente**.  
    3. **Permitir la conexión**y seleccione **siguiente**.
    4. Seleccione **dominio**y seleccione **siguiente**.
    5. Escriba cualquier nombre, como `MSDTC for Oracle EBS`y seleccione **finalizar**.
  
5.  Complete el asistente y cierre Firewall de Windows. 
  
## <a name="next"></a>Siguiente 
[Ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)