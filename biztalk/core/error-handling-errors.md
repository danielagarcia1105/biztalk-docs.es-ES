---
title: Error de control de errores | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 602be8a5-1f28-457d-8e12-ba06cff65491
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c494614465df4faeead9ec30d79dfdf47cc321c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999085"
---
# <a name="error-handling-errors"></a><span data-ttu-id="5675a-102">Errores de control de errores</span><span class="sxs-lookup"><span data-stu-id="5675a-102">Error Handling Errors</span></span>
<span data-ttu-id="5675a-103">Información para diagnosticar y resolver errores de control de errores de WCF.</span><span class="sxs-lookup"><span data-stu-id="5675a-103">Information for diagnosing and resolving WCF Error Handling errors.</span></span>  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a><span data-ttu-id="5675a-104">Las opciones de control de errores "Deshabilitar ubicación en caso de error" y "Suspender mensaje de solicitud en caso de error" no deben establecerse ambas como False</span><span class="sxs-lookup"><span data-stu-id="5675a-104">Error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false</span></span>    

|                 |                                                                                                <span data-ttu-id="5675a-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="5675a-105">Details</span></span>                                                                                                 |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5675a-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5675a-106">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="5675a-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5675a-107">Product Version</span></span> |                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                       |
|    <span data-ttu-id="5675a-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5675a-108">Event ID</span></span>     |                                                                                                   <span data-ttu-id="5675a-109">0</span><span class="sxs-lookup"><span data-stu-id="5675a-109">0</span></span>                                                                                                    |
|  <span data-ttu-id="5675a-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5675a-110">Event Source</span></span>   |                                                                                                   <span data-ttu-id="5675a-111">0</span><span class="sxs-lookup"><span data-stu-id="5675a-111">0</span></span>                                                                                                    |
|    <span data-ttu-id="5675a-112">Componente</span><span class="sxs-lookup"><span data-stu-id="5675a-112">Component</span></span>    |                                                                                                   <span data-ttu-id="5675a-113">0</span><span class="sxs-lookup"><span data-stu-id="5675a-113">0</span></span>                                                                                                    |
|  <span data-ttu-id="5675a-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5675a-114">Symbolic Name</span></span>  |                                                                                                   <span data-ttu-id="5675a-115">0</span><span class="sxs-lookup"><span data-stu-id="5675a-115">0</span></span>                                                                                                    |
|  <span data-ttu-id="5675a-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5675a-116">Message Text</span></span>   | <span data-ttu-id="5675a-117">Las opciones de control de errores "Deshabilitar ubicación en caso de error" y "Suspender mensaje de solicitud en caso de error" no deben establecerse ambas como False, ya que el mensaje podría perderse.</span><span class="sxs-lookup"><span data-stu-id="5675a-117">The error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="5675a-118">Establezca una o ambas opciones como True.</span><span class="sxs-lookup"><span data-stu-id="5675a-118">Please set one or both options to true</span></span> |

## <a name="explanation"></a><span data-ttu-id="5675a-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="5675a-119">Explanation</span></span>  
 <span data-ttu-id="5675a-120">En el adaptador de WCF-NetMsmq, las opciones **deshabilitar ubicación en caso de error** y **suspender mensaje de solicitud en caso de error** deben estar ambas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="5675a-120">In the WCF-NetMsmq adapter, the options **Disable location on failure** and **Suspend request message on failure** should not both be selected.</span></span> <span data-ttu-id="5675a-121">La pérdida del mensaje puede producirse cuando la ubicación de recepción continua recibiendo mensajes no válidos y estos mensajes no se suspenden y almacenan en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5675a-121">Message loss may occur as the receive location continues to receive invalid messages, while these messages are not suspended and stored in the Message Box.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5675a-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5675a-122">User Action</span></span>  
 <span data-ttu-id="5675a-123">Use el procedimiento siguiente para configurar las opciones del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5675a-123">Use the following procedure to configure adapter settings.</span></span>    

1. <span data-ttu-id="5675a-124">Abra **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="5675a-124">Open **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="5675a-125">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="5675a-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="5675a-126">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="5675a-126">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="5675a-127">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="5675a-127">Right-click the transport name.</span></span>  

5. <span data-ttu-id="5675a-128">Seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5675a-128">Select **Properties**.</span></span>  

6. <span data-ttu-id="5675a-129">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="5675a-129">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="5675a-130">Seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="5675a-130">Select **Configure**.</span></span>  

8. <span data-ttu-id="5675a-131">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, seleccione el **mensajes** ficha.</span><span class="sxs-lookup"><span data-stu-id="5675a-131">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, select the **Messages** tab.</span></span>  

9. <span data-ttu-id="5675a-132">En el **Error Handling** sección, asegúrese de cualquiera **deshabilitar ubicación en caso de error** o **suspender mensaje de solicitud en caso de error** está activada.</span><span class="sxs-lookup"><span data-stu-id="5675a-132">In the **Error Handling** section, ensure either **Disable location on failure** or **Suspend request message on failure** is checked.</span></span>
