---
title: Habilitar el Coordinador de transacciones distribuidas de MS permitir las transacciones de Oracle E-Business Suite | Documentos de Microsoft
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
ms.openlocfilehash: 0597c050e1531d71a62af04fe6c825653076297c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215076"
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a>Habilitar el Coordinador de transacciones distribuidas de MS permitir las transacciones de Oracle E-Business Suite
Configurar MSDTC para comenzar a crear aplicaciones que usan el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
Las operaciones se realizan sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el modelo de servicio WCF o el modelo de canal WCF) se pueden realizar en un ámbito de transacción. Si el programa de cliente tiene más de un recurso transaccional como parte de la misma transacción, la transacción obtiene elevada a una transacción MSDTC. Para habilitar el adaptador realizar operaciones dentro del ámbito de una transacción MSDTC, configurar MSDTC en el equipo que ejecuta el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]y en Oracle E-Business Suite. Además, agregue MSDTC a la lista de excepciones en el firewall, lo que puede ser el Firewall de Windows integrada. 
  
> [!NOTE]
>  Los pasos para configurar MSDTC varían para diferentes sistemas operativos. Los pasos enumerados en este tema se aplican al cliente de Windows y sistemas operativos Windows Server.  
  
## <a name="configure-msdtc"></a>Configurar MSDTC  
  
1.  Abra **servicios de componentes**.  

    O bien, en **el administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **servicios de componentes**.  
  
2.  Expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, expanda **Coordinador de transacciones distribuidas**, Haga clic en **DTC Local**y seleccione **propiedades**.  
  
3.  Seleccione la pestaña **Seguridad** . En esta ficha, seleccione todos los elementos siguientes: 

  - **Acceso a DTC desde la red**
  - **Permitir a clientes remotos** 
  - **Permitir entrantes** 
  - **Permitir salientes** 
  - **No hay Authetnication necesario**
  
4.  Seleccione **Aceptar** para guardar los cambios.  
  
5.  Si se le pide que reinicie el servicio MSDTC, seleccione **Sí**. Una vez reiniciado el servicio MSDTC, cierre las propiedades y la MMC de servicios de componentes. 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>Agregar MSDTC a la lista de excepciones de Firewall de Windows  

> [!TIP] 
>  Coordinador de transacción distribuida de Microsoft (MSDTC) se pueden permitirse ya en el firewall. Si es así, se muestra como una regla de entrada. Si no aparece, use esta sección para permitir MSDTC. 

1.  Abra **Firewall de Windows**y seleccione **configuración avanzada** a la izquierda.  

    O bien, en **el administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **Firewall de Windows con seguridad avanzada**.  
  
2.  Haga clic en **reglas de entrada**y seleccione **nueva regla**.  
  
3.  En el asistente: 

    1. Seleccione **programa**y seleccione **siguiente**. 
    2. Establecer el **la ruta del programa** a `%SystemRoot%\system32\msdtc.exe`y seleccione **siguiente**.  
    3. **Permitir la conexión**y seleccione **siguiente**.
    4. Seleccione **dominio**y seleccione **siguiente**.
    5. Escriba cualquier nombre, como `MSDTC for Oracle EBS`y seleccione **finalizar**.
  
5.  Complete el asistente y cierre Firewall de Windows. 
  
## <a name="next"></a>Siguiente 
[Ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)