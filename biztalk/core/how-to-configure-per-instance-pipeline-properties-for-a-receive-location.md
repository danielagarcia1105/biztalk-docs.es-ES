---
title: Cómo configurar propiedades de canalización por instancia para una ubicación de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- receive locations, configuring
- managing [pipelines], properties
- managing [pipelines], receive locations
- managing [receive locations], pipelines
- managing [pipelines], configuring
- pipelines, receive locations
- pipelines, configuring
- receive locations, pipelines
- managing [receive locations], configuring
ms.assetid: e1ed3b10-2f39-479b-a3e6-22b4b2872192
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e14483c5d17d968fc79126c65506720b501b6da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248844"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-receive-location"></a><span data-ttu-id="8a605-102">Cómo configurar propiedades de canalización por instancia para una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="8a605-102">How to Configure Per-instance Pipeline Properties for a Receive Location</span></span>
<span data-ttu-id="8a605-103">Este tema describe cómo utilizar la consola de administración de BizTalk Server para configurar propiedades de canalización para una ubicación de recepción después de que la canalización se haya implementado en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8a605-103">This topic describes how to use the BizTalk Server Administration console to configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="8a605-104">Los cambios que se efectúen solo sobrescriben las propiedades de canalización predeterminadas de esa ubicación de recepción, de modo que, si lo desea, podrá configurar propiedades de canalizaciones distintas para cada una de las ubicaciones de recepción del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8a605-104">Changes that you make overwrite the default pipeline properties for this receive location only, so if you want, you can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a605-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8a605-105">Prerequisites</span></span>  
 <span data-ttu-id="8a605-106">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8a605-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="8a605-107">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="8a605-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a605-108">Al usar propiedades de canalización por instancia para establecer el valor de la **DocumentSpecNames** propiedad en el componente de desensamblador XML de una canalización, el esquema de documento especificado y la canalización debe definirse en el mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="8a605-108">When using per-instance pipeline properties to set the value for the **DocumentSpecNames** property in the XML disassembler component of a pipeline, the specified document schema and the pipeline must be defined in the same project.</span></span>  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-receive-location"></a><span data-ttu-id="8a605-109">Para configurar propiedades de canalización por instancia para una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="8a605-109">To configure per-instance pipeline properties for a receive location</span></span>  
  
1.  <span data-ttu-id="8a605-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8a605-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="8a605-111">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la ubicación de recepción para el que se va a configurar las propiedades de canalización, **aplicaciones**y, a continuación, Expanda la aplicación que contiene la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="8a605-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the receive location for which to configure pipeline properties, expand **Applications**, and then expand the application containing the receive location.</span></span>  
  
3.  <span data-ttu-id="8a605-112">Haga clic en el **ubicaciones de recepción** carpeta, haga clic en la ubicación de recepción y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8a605-112">Click the **Receive Locations** folder, right-click the receive location, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8a605-113">Haga clic en el botón de puntos suspensivos (...) a la derecha de la **canalización de recepción** cuadro.</span><span class="sxs-lookup"><span data-stu-id="8a605-113">Click the ellipsis (…) to the right of the **Receive Pipeline** box.</span></span>  
  
5.  <span data-ttu-id="8a605-114">Configurar las propiedades que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8a605-114">Configure the properties you want, and then click **OK**.</span></span> <span data-ttu-id="8a605-115">Para obtener más información, haga clic en **ayuda** en la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8a605-115">For more information, click **Help** on the properties page.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8a605-116">Asegúrese de especificar información correcta para las propiedades de las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="8a605-116">Make sure that you enter correct information for pipelines properties.</span></span> <span data-ttu-id="8a605-117">Si escribe un valor no válido (una cadena en lugar de un número, por ejemplo), se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="8a605-117">If you enter an invalid value, for example a string rather than a number, it will generate an error.</span></span>  
  
6.  <span data-ttu-id="8a605-118">Si se trata de una respuesta de solicitud de ubicación de recepción, haga clic en el botón de puntos suspensivos (...) a la derecha de la **canalización de envío** cuadro.</span><span class="sxs-lookup"><span data-stu-id="8a605-118">If this is a request-response receive location, click the ellipsis (…) to the right of the **Send Pipeline** box.</span></span>  
  
7.  <span data-ttu-id="8a605-119">Configurar las propiedades que desee y, a continuación, haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="8a605-119">Configure the properties you want, and then click **OK** twice.</span></span> <span data-ttu-id="8a605-120">Para obtener más información, haga clic en **ayuda** en la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8a605-120">For more information, click **Help** on the properties page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a605-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a605-121">See Also</span></span>  
 <span data-ttu-id="8a605-122">[Administrar canalizaciones](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="8a605-122">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 <span data-ttu-id="8a605-123">[Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="8a605-123">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="8a605-124">Administrar ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="8a605-124">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)