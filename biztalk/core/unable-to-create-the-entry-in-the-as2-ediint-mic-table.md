---
title: No se puede crear la entrada en la tabla AS2 EDIINT MIC | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1c75d70-e39e-4465-b32b-db646c059c9b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c51cac2861fabaf8fc50269623130c90f3d445b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286700"
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a><span data-ttu-id="8d1ae-102">No se puede crear la entrada en la tabla AS2 EDIINT MIC</span><span class="sxs-lookup"><span data-stu-id="8d1ae-102">Unable to create the entry in the AS2 EDIINT MIC table</span></span>
## <a name="details"></a><span data-ttu-id="8d1ae-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d1ae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d1ae-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8d1ae-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8d1ae-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8d1ae-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8d1ae-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8d1ae-106">Event ID</span></span>|-|  
|<span data-ttu-id="8d1ae-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8d1ae-107">Event Source</span></span>|<span data-ttu-id="8d1ae-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d1ae-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="8d1ae-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8d1ae-109">Component</span></span>|<span data-ttu-id="8d1ae-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="8d1ae-110">AS2 Engine</span></span>|  
|<span data-ttu-id="8d1ae-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8d1ae-111">Symbolic Name</span></span>|<span data-ttu-id="8d1ae-112">AS2MicDataStoreCreateEntryError</span><span class="sxs-lookup"><span data-stu-id="8d1ae-112">AS2MicDataStoreCreateEntryError</span></span>|  
|<span data-ttu-id="8d1ae-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8d1ae-113">Message Text</span></span>|<span data-ttu-id="8d1ae-114">No se puede crear la entrada en la tabla AS2 EDIINT MIC.</span><span class="sxs-lookup"><span data-stu-id="8d1ae-114">Unable to create the entry in the AS2 EDIINT MIC table.</span></span> <span data-ttu-id="8d1ae-115">La razón puede ser la escritura de combinaciones de AS2-From, AS2-To y MessageID duplicadas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="8d1ae-115">This could be caused by duplicate AS2-From, AS2-To and MessageID combinations being written to the table.</span></span>  <span data-ttu-id="8d1ae-116">Error: {0}</span><span class="sxs-lookup"><span data-stu-id="8d1ae-116">Error: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8d1ae-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="8d1ae-117">Explanation</span></span>  
 <span data-ttu-id="8d1ae-118">Este error indica problemas de conexión de la base de datos o que las claves de la fila ya existen en la tabla de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d1ae-118">This error indicates either database connection problems or the row keys already exist in the database table.</span></span> <span data-ttu-id="8d1ae-119">El mensaje de error completo debe proporcionar información sobre por qué no se ha podido realizar la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="8d1ae-119">The full error message should provide information as to why the insert operation failed.</span></span> <span data-ttu-id="8d1ae-120">Las entradas de la tabla se quitan una vez que se haya recibido el MDN (sea con éxito o no), de modo que este error no debe volver a aparecer una vez recibido el MDN.</span><span class="sxs-lookup"><span data-stu-id="8d1ae-120">The entries in the table are removed after the MDN has been received (whether successful or failed), so this error should never happen after the MDN has been received.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d1ae-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8d1ae-121">User Action</span></span>  
 <span data-ttu-id="8d1ae-122">Para resolver este error, compruebe el mensaje de error completo para obtener información acerca de por qué no se pudo realizar la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="8d1ae-122">To resolve this error, check the full error message for information about why the insert operation failed.</span></span> <span data-ttu-id="8d1ae-123">En SQL, en la tabla EDIINT_MIC, determine si existen combinaciones AS2-From y AS2-To MessageID duplicadas.</span><span class="sxs-lookup"><span data-stu-id="8d1ae-123">In SQL, in the EDIINT_MIC table, determine whether there is duplicate AS2-From and AS2-To MessageID combinations.</span></span> <span data-ttu-id="8d1ae-124">Si es así, quítelas.</span><span class="sxs-lookup"><span data-stu-id="8d1ae-124">If so, remove them.</span></span>