---
title: Error de control de errores | Documentos de Microsoft
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
ms.openlocfilehash: dafc64afb24ce8bb7995e7852a778b17a556f018
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240828"
---
# <a name="error-handling-errors"></a><span data-ttu-id="697ec-102">Errores de control de errores</span><span class="sxs-lookup"><span data-stu-id="697ec-102">Error Handling Errors</span></span>
<span data-ttu-id="697ec-103">Información para diagnosticar y resolver errores de control de errores de WCF.</span><span class="sxs-lookup"><span data-stu-id="697ec-103">Information for diagnosing and resolving WCF Error Handling errors.</span></span>  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a><span data-ttu-id="697ec-104">Las opciones de control de errores "Deshabilitar ubicación en caso de error" y "Suspender mensaje de solicitud en caso de error" no deben establecerse ambas como False</span><span class="sxs-lookup"><span data-stu-id="697ec-104">Error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false</span></span>    
||<span data-ttu-id="697ec-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="697ec-105">Details</span></span>|  
|-|-|  
|<span data-ttu-id="697ec-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="697ec-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="697ec-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="697ec-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="697ec-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="697ec-108">Event ID</span></span>|<span data-ttu-id="697ec-109">0</span><span class="sxs-lookup"><span data-stu-id="697ec-109">0</span></span>|  
|<span data-ttu-id="697ec-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="697ec-110">Event Source</span></span>|<span data-ttu-id="697ec-111">0</span><span class="sxs-lookup"><span data-stu-id="697ec-111">0</span></span>|  
|<span data-ttu-id="697ec-112">Componente</span><span class="sxs-lookup"><span data-stu-id="697ec-112">Component</span></span>|<span data-ttu-id="697ec-113">0</span><span class="sxs-lookup"><span data-stu-id="697ec-113">0</span></span>|  
|<span data-ttu-id="697ec-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="697ec-114">Symbolic Name</span></span>|<span data-ttu-id="697ec-115">0</span><span class="sxs-lookup"><span data-stu-id="697ec-115">0</span></span>|  
|<span data-ttu-id="697ec-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="697ec-116">Message Text</span></span>|<span data-ttu-id="697ec-117">Las opciones de control de errores "Deshabilitar ubicación en caso de error" y "Suspender mensaje de solicitud en caso de error" no deben establecerse ambas como False, ya que el mensaje podría perderse.</span><span class="sxs-lookup"><span data-stu-id="697ec-117">The error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="697ec-118">Establezca una o ambas opciones como True.</span><span class="sxs-lookup"><span data-stu-id="697ec-118">Please set one or both options to true</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="697ec-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="697ec-119">Explanation</span></span>  
 <span data-ttu-id="697ec-120">En el adaptador de WCF-NetMsmq, las opciones de **deshabilitar ubicación en caso de error** y **suspender el mensaje de solicitud en caso de error** deben estar ambas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="697ec-120">In the WCF-NetMsmq adapter, the options **Disable location on failure** and **Suspend request message on failure** should not both be selected.</span></span> <span data-ttu-id="697ec-121">La pérdida del mensaje puede producirse cuando la ubicación de recepción continua recibiendo mensajes no válidos y estos mensajes no se suspenden y almacenan en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="697ec-121">Message loss may occur as the receive location continues to receive invalid messages, while these messages are not suspended and stored in the Message Box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="697ec-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="697ec-122">User Action</span></span>  
 <span data-ttu-id="697ec-123">Use el procedimiento siguiente para configurar las opciones del adaptador.</span><span class="sxs-lookup"><span data-stu-id="697ec-123">Use the following procedure to configure adapter settings.</span></span>    

1. <span data-ttu-id="697ec-124">Abra **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="697ec-124">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="697ec-125">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="697ec-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="697ec-126">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="697ec-126">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="697ec-127">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="697ec-127">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="697ec-128">Seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="697ec-128">Select **Properties**.</span></span>  
  
6.  <span data-ttu-id="697ec-129">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="697ec-129">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="697ec-130">Seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="697ec-130">Select **Configure**.</span></span>  
  
8.  <span data-ttu-id="697ec-131">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, seleccione la **mensajes** ficha.</span><span class="sxs-lookup"><span data-stu-id="697ec-131">In the **WCF [***transport type***] Transport Properties** dialog box, select the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="697ec-132">En el **control de errores** sección, asegúrese de cualquiera **deshabilitar ubicación en caso de error** o **suspender el mensaje de solicitud en caso de error** está activada.</span><span class="sxs-lookup"><span data-stu-id="697ec-132">In the **Error Handling** section, ensure either **Disable location on failure** or **Suspend request message on failure** is checked.</span></span>