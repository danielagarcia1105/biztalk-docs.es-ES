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
# <a name="configuring-transaction-set-list-edifact"></a><span data-ttu-id="7a0f8-102">Configuración de la lista de conjuntos de transacciones (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="7a0f8-102">Configuring Transaction Set List (EDIFACT)</span></span>
<span data-ttu-id="7a0f8-103">BizTalk Server permite definir una lista de conjuntos de transacciones que siempre debe incluir o excluir al procesar un intercambio EDI.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-103">BizTalk Server enables you to define a list of transaction sets that must always be included or excluded while processing an EDI interchange.</span></span> <span data-ttu-id="7a0f8-104">Esta sección proporciona instrucciones sobre cómo crear la lista de conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-104">This section provides instructions on how to create the transaction set list.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7a0f8-105">Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7a0f8-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7a0f8-106">Prerequisites</span></span>  
 <span data-ttu-id="7a0f8-107">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a0f8-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-a-transaction-set-list"></a><span data-ttu-id="7a0f8-108">Para configurar una lista de conjuntos de transacciones</span><span class="sxs-lookup"><span data-stu-id="7a0f8-108">To configure a transaction set list</span></span>  
  
1.  <span data-ttu-id="7a0f8-109">Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="7a0f8-109">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="7a0f8-110">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7a0f8-111">En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **transacciones Set List**.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-111">On a one-way agreement tab, under **Transaction Set Settings** section, click **Transaction Set List**.</span></span>  
  
3.  <span data-ttu-id="7a0f8-112">Seleccione **admitir conjuntos de transacciones de la lista** opción si desea crear una lista de conjuntos de transacciones que deba procesarse siempre.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-112">Select **Support Transaction Sets from the List** option if you want to create a list of transaction sets that must always be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a0f8-113">Use esta opción si normalmente recibe intercambios con tipos de transacción específicos, por ejemplo, APERAK.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-113">You would use this option if you typically receive interchanges with specific transaction types, say APERAK.</span></span> <span data-ttu-id="7a0f8-114">En ese caso, se agrega ese tipo de transacción a la lista para que los conjuntos de transacciones de otros tipos no se procesen.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-114">In that case, you add that transaction type to the list so that the transaction sets of other types are not processed at all.</span></span>  
  
4.  <span data-ttu-id="7a0f8-115">Seleccione **excluir conjuntos de transacciones de la lista** opción si desea crear una lista de conjuntos de transacciones que no deban procesarse.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-115">Select **Exclude Transaction Sets from the List** option if you want to create a list of transaction sets that must not be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a0f8-116">Use esta opción si normalmente recibe intercambios con tipos de transacción variados.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-116">You would use this option if you typically receive interchanges with varied transaction types.</span></span> <span data-ttu-id="7a0f8-117">En este caso, se agregan a la lista los tipos de transacción para los que no se obtiene ningún conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-117">In that case, you add those transaction type to the list for which you do not get any transaction sets.</span></span>  
  
5.  <span data-ttu-id="7a0f8-118">Haga clic en la celda vacía de la **UNH2.1** columna y en la lista desplegable, seleccione el conjunto de transacciones que desea admitir en la exclusión de tipo.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-118">Click the empty cell in the **UNH2.1** column and from the drop-down select the transaction set type you want to support on exclude.</span></span>  
  
6.  <span data-ttu-id="7a0f8-119">Para eliminar un tipo de transacción de la lista, seleccione la fila para el tipo de transacción y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-119">To delete a transaction type from the list, select the row for the transaction type, and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="7a0f8-120">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7a0f8-120">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0f8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a0f8-121">See Also</span></span>  
 [<span data-ttu-id="7a0f8-122">Configuración de valores del conjunto de transacciones (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="7a0f8-122">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)