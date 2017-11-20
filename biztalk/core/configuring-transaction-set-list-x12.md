---
title: Configurar conjunto de transacciones lista (X12) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f277318-90e9-4ad3-843a-e6128837fa2b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b11ea09c7c3156aea18b95d758228e55994901
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-transaction-set-list-x12"></a><span data-ttu-id="3281b-102">Configuración de la lista de conjuntos de transacciones (X12)</span><span class="sxs-lookup"><span data-stu-id="3281b-102">Configuring Transaction Set List (X12)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3281b-103"> permite definir una lista de conjuntos de transacciones que siempre se deben incluir o excluir al procesar un intercambio EDI.</span><span class="sxs-lookup"><span data-stu-id="3281b-103"> enables you to define a list of transaction sets that must always be included or excluded while processing an EDI interchange.</span></span> <span data-ttu-id="3281b-104">Esta sección proporciona instrucciones sobre cómo crear la lista de conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="3281b-104">This section provides instructions on how to create the transaction set list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3281b-105">La configuración descrita aquí también se aplica a los intercambios HIPAA.</span><span class="sxs-lookup"><span data-stu-id="3281b-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3281b-106">Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="3281b-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3281b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3281b-107">Prerequisites</span></span>  
 <span data-ttu-id="3281b-108">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3281b-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-a-transaction-set-list"></a><span data-ttu-id="3281b-109">Para configurar una lista de conjuntos de transacciones</span><span class="sxs-lookup"><span data-stu-id="3281b-109">To configure a transaction set list</span></span>  
  
1.  <span data-ttu-id="3281b-110">Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md).</span><span class="sxs-lookup"><span data-stu-id="3281b-110">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="3281b-111">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3281b-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3281b-112">En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **transacciones Set List**.</span><span class="sxs-lookup"><span data-stu-id="3281b-112">On a one-way agreement tab, under **Transaction Set Settings** section, click **Transaction Set List**.</span></span>  
  
3.  <span data-ttu-id="3281b-113">Seleccione **admitir conjuntos de transacciones de la lista** opción si desea crear una lista de conjuntos de transacciones que deba procesarse siempre.</span><span class="sxs-lookup"><span data-stu-id="3281b-113">Select **Support Transaction Sets from the List** option if you want to create a list of transaction sets that must always be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3281b-114">Use esta opción si normalmente recibe intercambios con tipos de transacción específicos, por ejemplo 850.</span><span class="sxs-lookup"><span data-stu-id="3281b-114">You would use this option if you typically receive interchanges with specific transaction types, say 850.</span></span> <span data-ttu-id="3281b-115">En ese caso, se agrega ese tipo de transacción a la lista para que los conjuntos de transacciones de otros tipos no se procesen.</span><span class="sxs-lookup"><span data-stu-id="3281b-115">In that case, you add that transaction type to the list so that the transaction sets of other types are not processed at all.</span></span>  
  
4.  <span data-ttu-id="3281b-116">Seleccione **excluir conjuntos de transacciones de la lista** opción si desea crear una lista de conjuntos de transacciones que no deban procesarse.</span><span class="sxs-lookup"><span data-stu-id="3281b-116">Select **Exclude Transaction Sets from the List** option if you want to create a list of transaction sets that must not be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3281b-117">Use esta opción si normalmente recibe intercambios con tipos de transacción variados.</span><span class="sxs-lookup"><span data-stu-id="3281b-117">You would use this option if you typically receive interchanges with varied transaction types.</span></span> <span data-ttu-id="3281b-118">En este caso, se agregan a la lista los tipos de transacción para los que no se obtiene ningún conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="3281b-118">In that case, you add those transaction type to the list for which you do not get any transaction sets.</span></span>  
  
5.  <span data-ttu-id="3281b-119">Haga clic en la celda vacía de la **ST01** columna y en la lista desplegable, seleccione el conjunto de transacciones que desea admitir en la exclusión de tipo.</span><span class="sxs-lookup"><span data-stu-id="3281b-119">Click the empty cell in the **ST01** column and from the drop-down select the transaction set type you want to support on exclude.</span></span>  
  
6.  <span data-ttu-id="3281b-120">Para eliminar un tipo de transacción de la lista, seleccione la fila para el tipo de transacción y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3281b-120">To delete a transaction type from the list, select the row for the transaction type, and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="3281b-121">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3281b-121">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3281b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3281b-122">See Also</span></span>  
 [<span data-ttu-id="3281b-123">Configurar transacción configurar (X12)</span><span class="sxs-lookup"><span data-stu-id="3281b-123">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)