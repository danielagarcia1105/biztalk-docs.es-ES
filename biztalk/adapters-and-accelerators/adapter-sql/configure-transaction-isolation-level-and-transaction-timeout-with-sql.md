---
title: Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55355272-60c0-49e4-b37e-9198458ab305
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2783b8741a7f8a703ad8aae22db5b114ea20f0b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013141"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-sql"></a>Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL
Al realizar operaciones de entrada (sondeo y la notificación) mediante el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe configurar correctamente el nivel de aislamiento de transacción y los valores de tiempo de espera de transacción. Para hacerlo:  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda el **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  

3. Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

4. Haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  

5. En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.  

6. En el panel izquierdo de la **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New** en el panel derecho para definir una nueva ubicación de recepción.  

7. En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **WCF-Custom** en el **tipo** lista.  

8. Haga clic en **configurar** adyacente a la **tipo** lista.  

9. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **comportamiento** ficha.  

10. En el **comportamiento** lista, haga clic en **ServiceBehavior**y haga clic en **Agregar extensión**.  

11. En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **sqlAdapterInboundTransactionBehavior**y haga clic en **Aceptar**.  

12. En el panel izquierdo de la **propiedades de transporte WCF-Custom**, seleccione el **sqlAdapterInboundTransactionBehavior** servicio bajo **ServiceBehavior**. Para recibir (mensaje de operación entrantes), uno puede utilizar el sqlAdapterInboundTransactionBehavior para controlar el nivel de aislamiento y el valor predeterminado es **ReadCommitted**.  

13. En el panel derecho de la **propiedades de transporte WCF-Custom**, especifique los valores adecuados para el **transactionIsolationLevel** y **transactionTimeout** parámetros. Puede seleccionar cualquiera de los siguientes niveles de aislamiento de transacción: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Instantánea**, **Chaos**, y **sin especificar**.  

    > [!NOTE]
    >  El valor predeterminado del nivel de aislamiento de transacción es **Serializable** para el adaptador de WCF-SQL para las operaciones de entrada y salidas. Para obtener información acerca de estos niveles de aislamiento de transacción, vea el **miembros** sección en [enumeración de nivel de aislamiento](http://go.microsoft.com/fwlink/?LinkId=126983) (http://go.microsoft.com/fwlink/?LinkId=126983).  

     ![Establecimiento del nivel de aislamiento de transacción](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")  

14. Haga clic en **Aceptar** en el **propiedades de transporte WCF-Custom** cuadro de diálogo.  

15. Haga clic en **Aceptar** en los cuadros de diálogo para guardar los cambios.
