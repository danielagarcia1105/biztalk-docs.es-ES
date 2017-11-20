---
title: "Opciones de configuración de autenticación para un puerto de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- authenticating, configuring
- managing [receive ports], authenticating
- receive ports, configuring
- configuring, authenticating
- configuring, receive ports
- authenticating, receive ports
ms.assetid: ce213ef0-ae91-47cf-84bf-0f86cc684bce
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 012ec38ef3d9acf53c7293c668b17cd85c6c738d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-authentication-options-for-a-receive-port"></a><span data-ttu-id="3e6c8-102">Cómo configurar opciones de autenticación para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="3e6c8-102">How to Configure Authentication Options for a Receive Port</span></span>
<span data-ttu-id="3e6c8-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar opciones de autenticación de mensajes para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-103">This topic describes how to use the BizTalk Server Administration console to configure message authentication options for a receive port.</span></span> <span data-ttu-id="3e6c8-104">Estas opciones entra en vigor cuando se configura la autenticación de resolución de entidades.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-104">These options take effect when party resolution authentication is configured.</span></span> <span data-ttu-id="3e6c8-105">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="3e6c8-105">The options are:</span></span>  
  
-   <span data-ttu-id="3e6c8-106">**Sin autenticación.**</span><span class="sxs-lookup"><span data-stu-id="3e6c8-106">**No authentication.**</span></span> <span data-ttu-id="3e6c8-107">Si se selecciona esta opción, el puerto de recepción pasará el mensaje sin comprobar las credenciales de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-107">If this option is selected, the receive port will pass the message through without checking for message credentials.</span></span>  
  
-   <span data-ttu-id="3e6c8-108">**Eliminar mensajes si hay errores de autenticación.**</span><span class="sxs-lookup"><span data-stu-id="3e6c8-108">**Drop messages if authentication fails.**</span></span> <span data-ttu-id="3e6c8-109">Si se selecciona esta opción, el puerto de recepción comprobará las credenciales de mensaje utilizando la resolución de entidades y descartará el mensaje si falla la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-109">If this option is selected, the receive port will check message credentials using Party resolution and discard the message if authentication fails.</span></span>  
  
-   <span data-ttu-id="3e6c8-110">**Conservar mensajes si hay errores de autenticación.**</span><span class="sxs-lookup"><span data-stu-id="3e6c8-110">**Keep messages if authentication fails.**</span></span> <span data-ttu-id="3e6c8-111">Si se selecciona esta opción, el puerto de recepción comprobará las credenciales de mensaje utilizando la resolución de entidades y mantendrá el mensaje en la cola de suspensión si falla la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-111">If this option is selected, the receive port will check message credentials using Party resolution and keep the message in the suspended queue if authentication fails.</span></span>  
  
 <span data-ttu-id="3e6c8-112">Para obtener instrucciones sobre cómo crear y configurar una entidad, consulte [cómo crear una entidad](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span><span class="sxs-lookup"><span data-stu-id="3e6c8-112">For instructions on creating and configuring a party, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span> <span data-ttu-id="3e6c8-113">Para obtener más información acerca de la autenticación de resolución de entidades, vea [autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md) y [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c8-113">For more information about party resolution authentication, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) and [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e6c8-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3e6c8-114">Prerequisites</span></span>  
 <span data-ttu-id="3e6c8-115">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3e6c8-116">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c8-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-authentication-options-for-a-receive-port"></a><span data-ttu-id="3e6c8-117">Para configurar opciones de autenticación para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="3e6c8-117">To configure authentication options for a receive port</span></span>  
  
1.  <span data-ttu-id="3e6c8-118">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3e6c8-119">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee configurar la autenticación de un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-119">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure authentication for a receive port.</span></span>  
  
3.  <span data-ttu-id="3e6c8-120">Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-120">Click **Receive Ports**, right-click the receive port, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3e6c8-121">En el **autenticación** sección, seleccione la opción que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3e6c8-121">In the **Authentication** section, select the option you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6c8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e6c8-122">See Also</span></span>  
 [<span data-ttu-id="3e6c8-123">Administrar puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="3e6c8-123">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)