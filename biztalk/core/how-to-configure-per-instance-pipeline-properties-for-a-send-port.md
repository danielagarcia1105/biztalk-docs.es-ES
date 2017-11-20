---
title: "Cómo configurar propiedades de canalización por instancia para un puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- managing [pipelines], properties
- configuring, send ports
- configuring, pipelines
- managing [pipelines], configuring
- managing [send ports], pipelines
- managing [send ports], configuring
- send ports, pipelines
- pipelines, configuring
ms.assetid: c58faa9e-0dfb-458b-8f1b-d3c91bce0436
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfb9927dca890a7f84baf372c4fa250a8ced17c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="3607c-102">Cómo configurar propiedades de canalización por instancia para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="3607c-102">How to Configure Per-Instance Pipeline Properties for a Send Port</span></span>
<span data-ttu-id="3607c-103">Este tema describe cómo utilizar la consola de administración de BizTalk Server para configurar propiedades de canalización para un puerto de envío después de que la canalización se haya implementado en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3607c-103">This topic describes how to use the BizTalk Server Administration console to configure pipeline properties for a send port after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="3607c-104">Los cambios que se efectúen sobrescriben las propiedades de canalización predeterminadas únicamente de este puerto de envío, de modo que, si lo desea, podrá configurar propiedades de canalizaciones distintas para cada uno de los puertos de envío del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3607c-104">Changes that you make overwrite the default pipeline properties for this send port only, so if you want, you can configure different pipeline properties for each send port in the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3607c-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3607c-105">Prerequisites</span></span>  
 <span data-ttu-id="3607c-106">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3607c-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3607c-107">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="3607c-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3607c-108">Al usar propiedades de canalización por instancia para establecer el valor de la **DocumentSpecNames** propiedad en el componente de desensamblador XML de una canalización, el esquema de documento especificado y la canalización debe definirse en el mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="3607c-108">When using per-instance pipeline properties to set the value for the **DocumentSpecNames** property in the XML disassembler component of a pipeline, the specified document schema and the pipeline must be defined in the same project.</span></span>  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="3607c-109">Para configurar propiedades de canalización por instancia para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="3607c-109">To configure per-instance pipeline properties for a send port</span></span>  
  
1.  <span data-ttu-id="3607c-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3607c-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3607c-111">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el puerto de envío para el que desea configurar las propiedades de canalización, **aplicaciones**y, a continuación, Expanda la aplicación que contiene el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="3607c-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the send port for which you want to configure pipeline properties, expand **Applications**, and then expand the application containing the send port.</span></span>  
  
3.  <span data-ttu-id="3607c-112">Haga clic en el **puertos de envío** carpeta, haga clic en el puerto de envío y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3607c-112">Click the **Send Ports** folder, right-click the send port, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3607c-113">Haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de la **canalización de envío** cuadro.</span><span class="sxs-lookup"><span data-stu-id="3607c-113">Click the ellipsis (**…**) button to the right of the **Send Pipeline** box.</span></span>  
  
5.  <span data-ttu-id="3607c-114">Configurar las propiedades que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3607c-114">Configure the properties you want, and then click **OK**.</span></span> <span data-ttu-id="3607c-115">Haga clic en **ayuda** en la página de propiedades para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3607c-115">Click **Help** on the properties page for more information.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3607c-116">Asegúrese de especificar información correcta para las propiedades de las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="3607c-116">Make sure that you enter correct information for pipelines properties.</span></span> <span data-ttu-id="3607c-117">Si escribe un valor no válido (una cadena en lugar de un número, por ejemplo), se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="3607c-117">If you enter an invalid value, for example a string rather than a number, it will generate an error.</span></span>  
  
6.  <span data-ttu-id="3607c-118">Si se trata de un puerto de envío de petición-respuesta, haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de la **canalización de recepción** cuadro.</span><span class="sxs-lookup"><span data-stu-id="3607c-118">If this is a solicit-response send port, click the ellipsis (**…**) button to the right of the **Receive Pipeline** box.</span></span>  
  
7.  <span data-ttu-id="3607c-119">Configurar las propiedades que desee y, a continuación, haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="3607c-119">Configure the properties you want, and then click **OK** twice.</span></span> <span data-ttu-id="3607c-120">Haga clic en **ayuda** en la página de propiedades para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3607c-120">Click **Help** on the properties page for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3607c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3607c-121">See Also</span></span>  
 <span data-ttu-id="3607c-122">[Administrar canalizaciones](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="3607c-122">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 <span data-ttu-id="3607c-123">[Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="3607c-123">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="3607c-124">Administrar ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="3607c-124">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)