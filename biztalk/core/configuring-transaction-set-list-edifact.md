---
title: Configurar conjunto de transacciones (EDIFACT) de la lista | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b03ace75-70bf-47c9-9a94-df813d7cab1e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a95feac48f7cb5137e95a34bf46c38811bb75c51
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-transaction-set-list-edifact"></a>Configuración de la lista de conjuntos de transacciones (EDIFACT)
BizTalk Server permite definir una lista de conjuntos de transacciones que siempre debe incluir o excluir al procesar un intercambio EDI. Esta sección proporciona instrucciones sobre cómo crear la lista de conjuntos de transacciones.  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-transaction-set-list"></a>Para configurar una lista de conjuntos de transacciones  
  
1.  Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **transacciones Set List**.  
  
3.  Seleccione **admitir conjuntos de transacciones de la lista** opción si desea crear una lista de conjuntos de transacciones que deba procesarse siempre.  
  
    > [!NOTE]
    >  Use esta opción si normalmente recibe intercambios con tipos de transacción específicos, por ejemplo, APERAK. En ese caso, se agrega ese tipo de transacción a la lista para que los conjuntos de transacciones de otros tipos no se procesen.  
  
4.  Seleccione **excluir conjuntos de transacciones de la lista** opción si desea crear una lista de conjuntos de transacciones que no deban procesarse.  
  
    > [!NOTE]
    >  Use esta opción si normalmente recibe intercambios con tipos de transacción variados. En este caso, se agregan a la lista los tipos de transacción para los que no se obtiene ningún conjunto de transacciones.  
  
5.  Haga clic en la celda vacía de la **UNH2.1** columna y en la lista desplegable, seleccione el conjunto de transacciones que desea admitir en la exclusión de tipo.  
  
6.  Para eliminar un tipo de transacción de la lista, seleccione la fila para el tipo de transacción y haga clic en **eliminar**.  
  
7.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de valores del conjunto de transacciones (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)