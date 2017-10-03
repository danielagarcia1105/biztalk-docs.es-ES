---
title: "Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con la base de datos de Oracle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b66e764-2330-441b-89ef-29118f27b366
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13d1beea3be34dbd818a94986fb8cae876bcdd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-database"></a>Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con la base de datos de Oracle
Al realizar la operación de entrada (sondeo) mediante la [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe configurar de manera adecuada el nivel de aislamiento de transacción y los valores de tiempo de espera de transacción. Para hacerlo:  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda el **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación de BizTalk que haya implementado después de generar los metadatos mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
4.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
5.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.  
  
6.  En el panel izquierdo de la **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New** en el panel derecho para definir una nueva ubicación de recepción.  
  
7.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **WCF-Custom** en el **tipo** lista.  
  
8.  Haga clic en **configurar** junto a la **tipo** lista.  
  
9. En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **comportamiento** ficha.  
  
10. En el **comportamiento** lista, haga clic en **ServiceBehavior**y haga clic en **Agregar extensión**.  
  
11. En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **oracleDBAdapterInboundTransactionBehavior**y haga clic en **Aceptar**.  
  
12. En el panel izquierdo de la **propiedades de transporte de WCF-Custom**, seleccione la **oracleDBAdapterInboundTransactionBehavior** servicio bajo **ServiceBehavior**.  
  
13. En el panel derecho de la **propiedades de transporte de WCF-Custom**, especifique los valores adecuados para el **transactionIsolationLevel** y **transactionTimeout** parámetros. Puede seleccionar cualquiera de los siguientes niveles de aislamiento de transacción: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Instantánea**, **Chaos**, y **sin especificar**. Para obtener información acerca de estos niveles de aislamiento de transacción, vea el **miembros** sección en [http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983).  
  
    > [!IMPORTANT]
    >  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite sólo los siguientes niveles de aislamiento de dos transacción: ReadCommitted y Serializable.  
  
     ![Establecer el nivel de aislamiento de transacción](../../adapters-and-accelerators/adapter-oracle-database/media/96a66f86-0321-4aa6-9e72-ada30d7de064.gif "96a66f86-0321-4aa6-9e72-ada30d7de064")  
  
14. Haga clic en **Aceptar** en el **propiedades de transporte de WCF-Custom** cuadro de diálogo.  
  
15. Haga clic en **Aceptar** en los cuadros de diálogo abiertos para guardar los cambios.