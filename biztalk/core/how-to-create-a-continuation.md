---
title: "Cómo crear una continuación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities, relating events
- tracking profiles, relating events
- continuations, tracking profiles
- activities, continuations
- events, relating
- orchestrations, business events
- tracking profiles, updating
- activities, tracking profiles
- tracking profiles, continuations
- tracking profiles, connecting activities
ms.assetid: 31d6fc24-676e-418c-8e78-1a46b045905d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e63983b290f0f4d7dff544cd2faea45f6cf46adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-continuation"></a><span data-ttu-id="94569-102">Cómo crear una continuación</span><span class="sxs-lookup"><span data-stu-id="94569-102">How to Create a Continuation</span></span>
<span data-ttu-id="94569-103">Se crean continuaciones para indicar qué eventos empresariales de una o varias orquestaciones están relacionados al construir actividades conectadas.</span><span class="sxs-lookup"><span data-stu-id="94569-103">You create continuations to indicate which business events in one or more orchestrations are related by constructing connected activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="94569-104">La actualización de un perfil de seguimiento puede afectar a las instancias de actividad en ejecución si la actividad incluye una continuación de BAM.</span><span class="sxs-lookup"><span data-stu-id="94569-104">Updating a tracking profile can impact activity instances in progress if the activity includes a BAM continuation.</span></span> <span data-ttu-id="94569-105">En concreto, si la actualización del perfil de seguimiento determina una intercepción descendente de datos para un elemento de actividad ya registrado, es posible que se sobrescriba el valor original.</span><span class="sxs-lookup"><span data-stu-id="94569-105">Specifically, if the update to the tracking profile specifies a downstream interception of data for an activity item already recorded, it is possible that the original value will be overwritten.</span></span> <span data-ttu-id="94569-106">Fundamentalmente, una única secuencia de eventos no se verá afectada por la aplicación de las actualizaciones de perfiles de seguimiento, ya que cada objeto de la secuencia está unido a una versión determinada del perfil que ya existía cuando se inició la actividad o secuencia.</span><span class="sxs-lookup"><span data-stu-id="94569-106">In essence, any single event stream will not be affected by the application of tracking profile updates because each stream object is tied to the specific version of the profile which was in place at the time the activity/stream started.</span></span>  <span data-ttu-id="94569-107">Sin embargo, ya que las continuaciones son el medio de correlacionar varias secuencias de eventos, las secuencias que todavía no hayan comenzado cuando se actualice el perfil, recogerán los cambios en las actualizaciones, lo que hace que sea posible la mencionada sobrescritura de datos.</span><span class="sxs-lookup"><span data-stu-id="94569-107">However, because continuations are the means of correlating multiple event streams, streams not yet begun at the time of a profile update will pick up the changes in the update, thus introducing the possible data overwrite described.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94569-108">Se pueden crear continuaciones con las orquestaciones que no procesan mensajes.</span><span class="sxs-lookup"><span data-stu-id="94569-108">You can create continuations with orchestrations that do not process messages.</span></span> <span data-ttu-id="94569-109">Se puede obtener la misma funcionalidad que la que se obtiene con las orquestaciones que procesan mensajes si se pasan llamadas de mensajes en curso entre orquestaciones y si se utiliza API BAM para procesar la continuación.</span><span class="sxs-lookup"><span data-stu-id="94569-109">You can obtain the same functionality as you can for orchestrations that do process messages by passing parameters in execution calls between orchestrations and by using BAM APIs to process the continuation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94569-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="94569-110">Prerequisites</span></span>  
 <span data-ttu-id="94569-111">Para llevar a cabo este procedimiento, deberá disponer de orquestaciones y definiciones de actividad de BAM a las que se pueda conectar.</span><span class="sxs-lookup"><span data-stu-id="94569-111">To perform this procedure, you must have deployed BAM activity definitions and orchestrations that you will connect to.</span></span>  
  
### <a name="to-create-a-continuation"></a><span data-ttu-id="94569-112">Para crear una continuación</span><span class="sxs-lookup"><span data-stu-id="94569-112">To create a continuation</span></span>  
  
1.  <span data-ttu-id="94569-113">Abra un perfil de seguimiento existente o cree un perfil de seguimiento nuevo.</span><span class="sxs-lookup"><span data-stu-id="94569-113">Open an existing tracking profile or create a tracking profile.</span></span> <span data-ttu-id="94569-114">Para obtener información acerca de cómo crear un perfil de seguimiento, vea [cómo crear un perfil de seguimiento](../core/how-to-create-a-tracking-profile.md).</span><span class="sxs-lookup"><span data-stu-id="94569-114">For information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="94569-115">Identificar un *token de continuación* que es un fragmento de información exclusiva que está disponible para las dos actividades.</span><span class="sxs-lookup"><span data-stu-id="94569-115">Identify a *continuation token,* which is a piece of unique information that is available to both activities.</span></span> <span data-ttu-id="94569-116">Por ejemplo, si un **CreditHistory** actividad se activa por un mensaje enviado desde un **LoanProcess** actividad dentro de un **EquityLoan**orquestación, el campo Nº de la mensaje se puede usar como un token de continuación ya que es común a ambas actividades.</span><span class="sxs-lookup"><span data-stu-id="94569-116">For example, if a **CreditHistory** activity is activated by a message sent from a **LoanProcess** activity within an **EquityLoan**orchestration, the SSN field of the message can be used as a continuation token because it is common to both activities.</span></span>  
  
3.  <span data-ttu-id="94569-117">Haga clic en la actividad y, a continuación, seleccione **nueva Continuation** para crear una continuación (CreditHistory).</span><span class="sxs-lookup"><span data-stu-id="94569-117">Right-click the activity and then select **New Continuation** to create a continuation (CreditHistory).</span></span> <span data-ttu-id="94569-118">Asigne un nombre al nodo de continuación que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="94569-118">Name the continuation node you just created.</span></span>  
  
4.  <span data-ttu-id="94569-119">Desde la vista Programación de orquestación, seleccione el token de continuación que eligió en el paso 2, como el Nº de SS (en este caso, desde la acción Envío) y arrástrelo al nodo de continuación que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="94569-119">From the Orchestration Schedule View, select the continuation token you chose in step 2, such as SSN (in this case from the Send action) and drop it into the continuation node you created in step 3.</span></span>  
  
5.  <span data-ttu-id="94569-120">Haga clic en la actividad y seleccione **nuevo ContinuationID** para crear un nodo de Id. de continuación.</span><span class="sxs-lookup"><span data-stu-id="94569-120">Right-click the activity and select **New ContinuationID** to create a Continuation ID node.</span></span> <span data-ttu-id="94569-121">Asígnele un nombre que sea exactamente el mismo que eligió en le paso 3 y arrástrelo al nodo que contenga el elemento de datos correspondiente (en este caso, Nº de SS desde la acción Recepción).</span><span class="sxs-lookup"><span data-stu-id="94569-121">Name it using the name you chose in step 3, and drop it in the node that contains the corresponding data item (in this case, SSN from the Receive action).</span></span>  
  
6.  <span data-ttu-id="94569-122">En el **archivo**menú, haga clic en **Guardar como**para guardar el perfil de seguimiento como un archivo .btt a la base de datos de administración de BizTalk y para evitar sobrescribir los archivos existentes de btt.</span><span class="sxs-lookup"><span data-stu-id="94569-122">On the **File**menu, click **Save As**to save the tracking profile as a .btt file to the BizTalk Management database and to avoid overwriting any existing .btt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94569-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="94569-123">See Also</span></span>  
 <span data-ttu-id="94569-124">[Nodos Continuation y ContinuationID](../core/continuation-and-continuationid-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="94569-124">[Continuation and ContinuationID Nodes](../core/continuation-and-continuationid-nodes.md) </span></span>  
 [<span data-ttu-id="94569-125">Creación de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="94569-125">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)