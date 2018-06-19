---
title: Restringido intervalos de caracteres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e12213bf-750e-43a2-998a-949fa4255b73
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74f1399aaa828d5c23c2600ebabeb7063a982447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268292"
---
# <a name="restricted-character-ranges"></a><span data-ttu-id="8d55c-102">Intervalos de caracteres restringidos</span><span class="sxs-lookup"><span data-stu-id="8d55c-102">Restricted Character Ranges</span></span>

## <a name="overview"></a><span data-ttu-id="8d55c-103">Información general</span><span class="sxs-lookup"><span data-stu-id="8d55c-103">Overview</span></span>
<span data-ttu-id="8d55c-104">Al crear un esquema para los mensajes de archivo sin formato, puede dirigir [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para bloquear un determinado carácter o un intervalo de caracteres desde la que se incluye en los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="8d55c-104">When creating a schema for flat file messages, you can direct [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to block a particular character or a range of characters from being included in any outgoing message.</span></span> <span data-ttu-id="8d55c-105">Para ello, en el Editor de BizTalk, abra un esquema que vaya a usar como esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8d55c-105">To do this, in BizTalk Editor, open a schema that is to be used as a destination schema.</span></span> <span data-ttu-id="8d55c-106">Seleccione el **esquema** nodo y el uso del **caracteres restringidos** propiedad para abrir el **caracteres restringidos** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8d55c-106">Select the **Schema** node and the use the **Restricted Characters** property to open the **Restricted Characters** dialog box.</span></span> <span data-ttu-id="8d55c-107">Escriba el carácter de intervalos que desea que se incluyan en los mensajes enviados por BizTalk Server y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8d55c-107">Enter the character range(s) that you want to prevent being included in any message sent by BizTalk Server, and then click **OK**.</span></span> <span data-ttu-id="8d55c-108">Cada vez que BizTalk Server intenta procesar un carácter especificado en el **caracteres restringidos** cuadro de diálogo de un esquema de destino de procesamiento se detiene y un mensaje de error se genera.</span><span class="sxs-lookup"><span data-stu-id="8d55c-108">Whenever BizTalk Server attempts to process a character specified in the **Restricted Characters** dialog box of a destination schema, processing stops and an error message is generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d55c-109">En BizTalk Server, la restricción de intervalos de caracteres es una función de Extensión de archivo sin formato y, como tal, no es aplicable a los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="8d55c-109">In BizTalk Server, character range restriction is a function of the Flat File Extension, and as such, does not apply to XML messages.</span></span> <span data-ttu-id="8d55c-110">Las extensiones que se pueden ofrecer en el futuro para los distintos tipos de mensajes pueden ser distintas en cuanto al modo de implementar la restricción de los intervalos de caracteres para los formatos de mensajes compatibles.</span><span class="sxs-lookup"><span data-stu-id="8d55c-110">Extensions that might be offered in the future for different types of messages might differ in how they implement character range restriction for their supported message formats.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d55c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d55c-111">See Also</span></span>  
-  [<span data-ttu-id="8d55c-112">Consideraciones al crear sin formato de archivo esquemas de mensaje</span><span class="sxs-lookup"><span data-stu-id="8d55c-112">Considerations When Creating Flat File Message Schemas</span></span>](../core/considerations-when-creating-flat-file-message-schemas.md)   
-  <span data-ttu-id="8d55c-113">**Caracteres restringidos (propiedad de nodo de esquemas de archivo sin formato**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="8d55c-113">**Restricted Characters (Node Property of Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>