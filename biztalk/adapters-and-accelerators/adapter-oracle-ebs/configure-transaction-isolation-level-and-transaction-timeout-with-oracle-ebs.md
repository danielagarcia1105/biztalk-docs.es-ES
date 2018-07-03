---
title: Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite | Microsoft Docs
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
ms.openlocfilehash: 8bbff645105feb4732afdf86aa3a591252c0d88c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969221"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-e-business-suite"></a>Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite
Al realizar operaciones de entrada (sondeo y la notificación) mediante el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe configurar correctamente el nivel de aislamiento de transacción y los valores de tiempo de espera de transacción. Para hacerlo:  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda el **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  

3. Expanda la aplicación de BizTalk que ha implementado después de generar los metadatos mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  

4. Haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  

5. En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.  

6. En el panel izquierdo de la **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New** en el panel derecho para definir una nueva ubicación de recepción.  

7. En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **WCF-Custom** en el **tipo** lista.  

8. Haga clic en **configurar** adyacente a la **tipo** lista.  

9. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **comportamiento** ficha.  

10. En el **comportamiento** lista, haga clic en **ServiceBehavior**y haga clic en **Agregar extensión**.  

11. En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **oracleEBSAdapterInboundTransactionBehavior**y haga clic en **Aceptar**.  

12. En el panel izquierdo de la **propiedades de transporte WCF-Custom**, seleccione el **oracleEBSAdapterInboundTransactionBehavior** servicio bajo **ServiceBehavior**.  

13. En el panel derecho de la **propiedades de transporte WCF-Custom**, especifique los valores adecuados para el **transactionIsolationLevel** y **transactionTimeout** parámetros. Puede seleccionar cualquiera de los siguientes niveles de aislamiento de transacción: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Instantánea**, **Chaos**, y **sin especificar**. Para obtener información acerca de estos niveles de aislamiento de transacción, vea el **miembros** sección en [ http://go.microsoft.com/fwlink/?LinkId=126983 ](http://go.microsoft.com/fwlink/?LinkId=126983).  

    > [!IMPORTANT]
    >  Oracle E-Business Suite admite solo los siguientes niveles de aislamiento de dos transacción: ReadCommitted y Serializable.  

     ![Establecimiento del nivel de aislamiento de transacción](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")  

14. Haga clic en **Aceptar** en el **propiedades de transporte WCF-Custom** cuadro de diálogo.  

15. Haga clic en **Aceptar** en los cuadros de diálogo para guardar los cambios.
