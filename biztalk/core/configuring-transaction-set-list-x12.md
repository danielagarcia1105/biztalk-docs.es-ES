---
title: Configurar conjunto de transacciones lista (X12) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f277318-90e9-4ad3-843a-e6128837fa2b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b11ea09c7c3156aea18b95d758228e55994901
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233444"
---
# <a name="configuring-transaction-set-list-x12"></a>Configuración de la lista de conjuntos de transacciones (X12)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite definir una lista de conjuntos de transacciones que siempre se deben incluir o excluir al procesar un intercambio EDI. Esta sección proporciona instrucciones sobre cómo crear la lista de conjuntos de transacciones.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a los intercambios HIPAA.  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-transaction-set-list"></a>Para configurar una lista de conjuntos de transacciones  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **transacciones Set List**.  
  
3.  Seleccione **admitir conjuntos de transacciones de la lista** opción si desea crear una lista de conjuntos de transacciones que deba procesarse siempre.  
  
    > [!NOTE]
    >  Use esta opción si normalmente recibe intercambios con tipos de transacción específicos, por ejemplo 850. En ese caso, se agrega ese tipo de transacción a la lista para que los conjuntos de transacciones de otros tipos no se procesen.  
  
4.  Seleccione **excluir conjuntos de transacciones de la lista** opción si desea crear una lista de conjuntos de transacciones que no deban procesarse.  
  
    > [!NOTE]
    >  Use esta opción si normalmente recibe intercambios con tipos de transacción variados. En este caso, se agregan a la lista los tipos de transacción para los que no se obtiene ningún conjunto de transacciones.  
  
5.  Haga clic en la celda vacía de la **ST01** columna y en la lista desplegable, seleccione el conjunto de transacciones que desea admitir en la exclusión de tipo.  
  
6.  Para eliminar un tipo de transacción de la lista, seleccione la fila para el tipo de transacción y haga clic en **eliminar**.  
  
7.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar transacción configurar (X12)](../core/configuring-transaction-set-settings-x12.md)