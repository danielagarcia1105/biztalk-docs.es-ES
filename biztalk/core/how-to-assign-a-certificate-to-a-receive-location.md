---
title: "Cómo asignar un certificado a una ubicación de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 54ae300e-62c5-480f-a9b7-e5c3457a0f80
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94554aa5781ed609e5129d58ab75e5709e432278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-a-certificate-to-a-receive-location"></a><span data-ttu-id="3f442-102">Cómo asignar un certificado a una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="3f442-102">How to Assign a Certificate to a Receive Location</span></span>
<span data-ttu-id="3f442-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para asignar un certificado de seguridad a una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="3f442-103">This topic describes how to use the BizTalk Server Administration console to assign a security certificate to a receive location.</span></span> <span data-ttu-id="3f442-104">Este procedimiento sólo debe realizarse en una ubicación de recepción bidireccional.</span><span class="sxs-lookup"><span data-stu-id="3f442-104">You can perform this procedure on a two-way receive location only.</span></span> <span data-ttu-id="3f442-105">El certificado debe existir en el almacén de certificados Otras personas del equipo en el que se ejecuta BizTalk Server o, de lo contrario, no se procesarán los mensajes asociados con esta ubicación de recepción y se registrarán errores.</span><span class="sxs-lookup"><span data-stu-id="3f442-105">The certificate must exist in the Other People certificate store on the computer running BizTalk Server, or messages associated with this receive location will not be processed, and errors will be logged.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3f442-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3f442-106">Prerequisites</span></span>  
 <span data-ttu-id="3f442-107">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3f442-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3f442-108">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="3f442-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-assign-a-certificate-to-a-receive-location"></a><span data-ttu-id="3f442-109">Para asignar un certificado a una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="3f442-109">To assign a certificate to a receive location</span></span>  
  
1.  <span data-ttu-id="3f442-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3f442-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3f442-111">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee asignar un certificado a una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="3f442-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to assign a certificate to a receive location.</span></span>  
  
3.  <span data-ttu-id="3f442-112">Expanda **ubicaciones de recepción**, haga clic en la ubicación de recepción, haga clic en **propiedades**y, a continuación, haga clic en **certificado**.</span><span class="sxs-lookup"><span data-stu-id="3f442-112">Expand **Receive Locations**, right-click the receive location, click **Properties**, and then click **Certificate**.</span></span>  
  
4.  <span data-ttu-id="3f442-113">Si el certificado existe en el equipo local, haga clic en **examinar**, busque el certificado que desea asignar a esta ubicación de recepción y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f442-113">If the certificate exists on the local computer, click **Browse**, browse to the certificate that you want to assign to this receive location, and then click **OK**.</span></span> <span data-ttu-id="3f442-114">De lo contrario, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="3f442-114">Otherwise, skip this step.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3f442-115">Si realiza esta operación desde un equipo remoto, asegúrese de que exista el certificado en el equipo en que se ejecute BizTalk Server y no sólo en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="3f442-115">If you are performing this operation from a remote computer, make sure that the certificate exists on the computer running BizTalk Server, and not only on the local computer.</span></span> <span data-ttu-id="3f442-116">En caso contrario, la ubicación de recepción no podrá procesar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="3f442-116">Otherwise, the receive location will not be able to process messages.</span></span>  
  
5.  <span data-ttu-id="3f442-117">Si el certificado no existe en el equipo local, en la **huella digital** , escriba o pegue la huella digital del certificado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f442-117">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="3f442-118">La huella digital de certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3f442-118">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f442-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f442-119">See Also</span></span>  
 [<span data-ttu-id="3f442-120">Administrar ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="3f442-120">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)