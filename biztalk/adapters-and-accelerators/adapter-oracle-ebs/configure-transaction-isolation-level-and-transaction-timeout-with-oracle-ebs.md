---
title: Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db3d64ad-037d-486a-bdde-45c8199613f1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89e818d6ca3fdda05ee877f9e6ef4f04d7a66176
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215844"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-e-business-suite"></a>Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite
Al realizar operaciones de entrada (sondeo y la notificación) mediante la [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe configurar de manera adecuada el nivel de aislamiento de transacción y los valores de tiempo de espera de transacción. Para hacerlo:  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda el **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación de BizTalk que haya implementado después de generar los metadatos mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
4.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
5.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.  
  
6.  En el panel izquierdo de la **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New** en el panel derecho para definir una nueva ubicación de recepción.  
  
7.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **WCF-Custom** en el **tipo** lista.  
  
8.  Haga clic en **configurar** junto a la **tipo** lista.  
  
9. En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **comportamiento** ficha.  
  
10. En el **comportamiento** lista, haga clic en **ServiceBehavior**y haga clic en **Agregar extensión**.  
  
11. En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **oracleEBSAdapterInboundTransactionBehavior**y haga clic en **Aceptar**.  
  
12. En el panel izquierdo de la **propiedades de transporte de WCF-Custom**, seleccione la **oracleEBSAdapterInboundTransactionBehavior** servicio bajo **ServiceBehavior**.  
  
13. En el panel derecho de la **propiedades de transporte de WCF-Custom**, especifique los valores adecuados para el **transactionIsolationLevel** y **transactionTimeout** parámetros. Puede seleccionar cualquiera de los siguientes niveles de aislamiento de transacción: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Instantánea**, **Chaos**, y **sin especificar**. Para obtener información acerca de estos niveles de aislamiento de transacción, vea el **miembros** sección en [http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983).  
  
    > [!IMPORTANT]
    >  Oracle E-Business Suite admite sólo los siguientes niveles de aislamiento de dos transacción: ReadCommitted y Serializable.  
  
     ![Establecer el nivel de aislamiento de transacción](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")  
  
14. Haga clic en **Aceptar** en el **propiedades de transporte de WCF-Custom** cuadro de diálogo.  
  
15. Haga clic en **Aceptar** en los cuadros de diálogo abiertos para guardar los cambios.