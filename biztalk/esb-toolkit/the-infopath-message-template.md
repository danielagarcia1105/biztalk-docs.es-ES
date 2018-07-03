---
title: La plantilla de mensaje de InfoPath | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb055b1-8480-44dd-8739-f2981bca63c3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c929e8ef1edcd88c0976d145354779b3e095634
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024474"
---
# <a name="the-infopath-message-template"></a><span data-ttu-id="a1165-102">La plantilla de mensaje de InfoPath</span><span class="sxs-lookup"><span data-stu-id="a1165-102">The InfoPath Message Template</span></span>
<span data-ttu-id="a1165-103">Como alternativa a la visualización de los mensajes de error ESB en el Portal de administración de ESB, los usuarios pueden aprovechar una plantilla de mensaje de Microsoft InfoPath denominada el Visor de mensajes de excepción de ESB proporcionado con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1165-103">As an alternative to viewing ESB fault messages in the ESB Management Portal, users can take advantage of a Microsoft InfoPath message template named the ESB Exception Message Viewer, provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="a1165-104">El marco de administración de excepciones de ESB puede conservar los mensajes en un formato serializado que, junto con la plantilla de Visor de mensajes de excepción de ESB mostrará varias vistas del mensaje de error y los mensajes originales que contiene.</span><span class="sxs-lookup"><span data-stu-id="a1165-104">The ESB Exception Management Framework can persist messages in a serialized format that, together with the ESB Exception Message Viewer template, will display several views of the fault message and the original messages it contains.</span></span> <span data-ttu-id="a1165-105">El Visor de mensajes de excepción de ESB proporciona las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="a1165-105">The ESB Exception Message Viewer provides the following views:</span></span>  
  
- <span data-ttu-id="a1165-106">Vista General</span><span class="sxs-lookup"><span data-stu-id="a1165-106">General view</span></span>  
  
- <span data-ttu-id="a1165-107">Vista de objeto de excepción</span><span class="sxs-lookup"><span data-stu-id="a1165-107">Exception Object view</span></span>  
  
- <span data-ttu-id="a1165-108">vista Mensaje</span><span class="sxs-lookup"><span data-stu-id="a1165-108">Messages view</span></span>  
  
  <span data-ttu-id="a1165-109">Figura 1 muestra la vista General del Visor de mensaje de excepción de ESB, que muestra más propiedades de ambiente de la excepción.</span><span class="sxs-lookup"><span data-stu-id="a1165-109">Figure 1 shows the General view of the ESB Exception Message Viewer, which displays most ambient properties of the exception.</span></span>  
  
  <span data-ttu-id="a1165-110">![Vista General de mensajes de excepción](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")</span><span class="sxs-lookup"><span data-stu-id="a1165-110">![Exception Message General View](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")</span></span>  
  
  <span data-ttu-id="a1165-111">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="a1165-111">**Figure 1**</span></span>  
  
  <span data-ttu-id="a1165-112">**El Visor de mensajes de excepción de ESB que muestra la vista General**</span><span class="sxs-lookup"><span data-stu-id="a1165-112">**The ESB Exception Message Viewer showing the General view**</span></span>  
  
  <span data-ttu-id="a1165-113">La figura 2 muestra la vista del objeto de excepción, que muestra las propiedades y el seguimiento de pila de la **System.Exception** objeto.</span><span class="sxs-lookup"><span data-stu-id="a1165-113">Figure 2 shows the Exception Object view, which displays the properties and the stack trace from the **System.Exception** object.</span></span>  
  
  <span data-ttu-id="a1165-114">![Objeto de excepción del mensaje de excepción](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")</span><span class="sxs-lookup"><span data-stu-id="a1165-114">![Exception Message Exception Object](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")</span></span>  
  
  <span data-ttu-id="a1165-115">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="a1165-115">**Figure 2**</span></span>  
  
  <span data-ttu-id="a1165-116">**El Visor de mensajes de excepción de ESB que muestra la vista del objeto de excepción**</span><span class="sxs-lookup"><span data-stu-id="a1165-116">**The ESB Exception Message Viewer showing the Exception Object view**</span></span>  
  
  <span data-ttu-id="a1165-117">Figura 3 se muestra la vista de mensajes, que proporciona una lista desplegable desde el que el usuario puede seleccionar desde mensajes conservados disponibles.</span><span class="sxs-lookup"><span data-stu-id="a1165-117">Figure 3 shows the Messages view, which provides a drop-down list from which the user can select from available persisted messages.</span></span> <span data-ttu-id="a1165-118">La vista muestra los valores de las propiedades de contexto del mensaje persistente y el contenido del mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="a1165-118">The view displays the values of the context properties of the persisted message and the XML message content.</span></span>  
  
  <span data-ttu-id="a1165-119">![Mensaje de excepción la vista mensajes](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")</span><span class="sxs-lookup"><span data-stu-id="a1165-119">![Exception Message Messages View](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")</span></span>  
  
  <span data-ttu-id="a1165-120">**Figura 3**</span><span class="sxs-lookup"><span data-stu-id="a1165-120">**Figure 3**</span></span>  
  
  <span data-ttu-id="a1165-121">**El Visor de mensajes de excepción de ESB que muestra la vista mensajes**</span><span class="sxs-lookup"><span data-stu-id="a1165-121">**The ESB Exception Message Viewer showing the Messages view**</span></span>