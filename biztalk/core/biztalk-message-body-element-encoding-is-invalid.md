---
title: Codificación de elemento de cuerpo de mensaje de BizTalk Server no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6bca7046606461dd3368224364c21dd48ea5dfb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967973"
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a><span data-ttu-id="b3884-102">Codificación de elemento de cuerpo de mensaje de BizTalk no válida</span><span class="sxs-lookup"><span data-stu-id="b3884-102">BizTalk message body element encoding is invalid</span></span>
## <a name="details"></a><span data-ttu-id="b3884-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b3884-103">Details</span></span>  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b3884-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b3884-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="b3884-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b3884-105">Product Version</span></span> |                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                           |
|    <span data-ttu-id="b3884-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b3884-106">Event ID</span></span>     |                                                       <span data-ttu-id="b3884-107">0</span><span class="sxs-lookup"><span data-stu-id="b3884-107">0</span></span>                                                        |
|  <span data-ttu-id="b3884-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b3884-108">Event Source</span></span>   |                                                       <span data-ttu-id="b3884-109">0</span><span class="sxs-lookup"><span data-stu-id="b3884-109">0</span></span>                                                        |
|    <span data-ttu-id="b3884-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b3884-110">Component</span></span>    |                                                       <span data-ttu-id="b3884-111">0</span><span class="sxs-lookup"><span data-stu-id="b3884-111">0</span></span>                                                        |
|  <span data-ttu-id="b3884-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b3884-112">Symbolic Name</span></span>  |                                                       <span data-ttu-id="b3884-113">0</span><span class="sxs-lookup"><span data-stu-id="b3884-113">0</span></span>                                                        |
|  <span data-ttu-id="b3884-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b3884-114">Message Text</span></span>   | <span data-ttu-id="b3884-115">Codificación del elemento del cuerpo del mensaje de BizTalk "{0}" no es válido.</span><span class="sxs-lookup"><span data-stu-id="b3884-115">BizTalk message body element encoding "{0}" is invalid.</span></span> <span data-ttu-id="b3884-116">Codificación esperada: "xml", "base64", "hex" o "string"</span><span class="sxs-lookup"><span data-stu-id="b3884-116">Expected encoding: "xml", "base64", "hex", or "string"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b3884-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b3884-117">Explanation</span></span>  
 <span data-ttu-id="b3884-118">Este error indica el uso de la opción de plantilla de cuerpo de BizTalk para los mensajes salientes. Sin embargo, el tipo de codificación especificado para el cuerpo de BizTalk no es válido.</span><span class="sxs-lookup"><span data-stu-id="b3884-118">This error indicates the use of the BizTalk body template option for the outgoing messages; however, the encoding type specified for the BizTalk body is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b3884-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b3884-119">User Action</span></span>  
 <span data-ttu-id="b3884-120">Use el procedimiento siguiente para configurar el tipo de codificación.</span><span class="sxs-lookup"><span data-stu-id="b3884-120">Use the following procedure to configure the encoding type.</span></span>  
  
#### <a name="to-configure-the-encoding-type"></a><span data-ttu-id="b3884-121">Para configurar el tipo de codificación</span><span class="sxs-lookup"><span data-stu-id="b3884-121">To configure the encoding type</span></span>  
  
1. <span data-ttu-id="b3884-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="b3884-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="b3884-123">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b3884-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="b3884-124">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="b3884-124">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="b3884-125">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="b3884-125">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="b3884-126">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b3884-126">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="b3884-127">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="b3884-127">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="b3884-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="b3884-128">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="b3884-129">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **mensajes** ficha.</span><span class="sxs-lookup"><span data-stu-id="b3884-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="b3884-130">En el **cuerpo del mensaje saliente de WCF** sección, haga clic en el **plantilla – contenido especificado por plantilla** botón de radio.</span><span class="sxs-lookup"><span data-stu-id="b3884-130">In the **Outbound WCF message body** section, click the **Template – Content specified by template** radio button.</span></span> <span data-ttu-id="b3884-131">En el **XML** cuadro de texto, debe ser el formato del cuerpo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b3884-131">In the **XML** text box, the format of the BizTalk body should be</span></span>   
    <span data-ttu-id="b3884-132">\<**BTS-msg-body xmlns = "<http://www.microsoft.com/schemas/bts2007>" encoding = "[xml&#124;base64&#124;hexadecimal&#124;string]" /** \> (los valores válidos, que distinguen mayúsculas de minúsculas, para la codificación son xml&#124;base64&#124;hexadecimal&#124;cadena)</span><span class="sxs-lookup"><span data-stu-id="b3884-132">\<**bts-msg-body xmlns="<http://www.microsoft.com/schemas/bts2007>" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>  (valid values, which are case-sensitive, for encoding are xml&#124;base64&#124;hex&#124;string)</span></span>