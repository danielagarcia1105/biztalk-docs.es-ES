---
title: "Cómo asignar un certificado a un puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, assigning
- managing [send ports], certificates
- assigning certificates
- certificates, send ports
ms.assetid: ba9e9c8b-f5b6-4fee-9e89-31b0f1df6ed4
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec19c845c6b0cfb5d19bd7a961fe9ddfbcf2a3d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-a-certificate-to-a-send-port"></a><span data-ttu-id="65412-102">Cómo asignar un certificado a un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="65412-102">How to Assign a Certificate to a Send Port</span></span>
<span data-ttu-id="65412-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para asignar un certificado de seguridad a un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="65412-103">This topic describes how to use the BizTalk Server Administration console to assign a security certificate to a send port.</span></span> <span data-ttu-id="65412-104">El certificado debe existir en el almacén de certificados Otras personas del equipo en el que se ejecuta BizTalk Server o, de lo contrario, no se procesarán los mensajes asociados con este puerto de envío y se registrarán errores.</span><span class="sxs-lookup"><span data-stu-id="65412-104">The certificate must exist in the Other People certificate store on the computer running BizTalk Server, or messages associated with this send port will not be processed, and errors will be logged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65412-105">El desarrollador de aplicaciones puede asignar un certificado de seguridad a un puerto de envío durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="65412-105">The application developer can assign a security certificate to a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="65412-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="65412-106">Prerequisites</span></span>  
 <span data-ttu-id="65412-107">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="65412-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="65412-108">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="65412-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-assign-a-certificate-to-a-send-port"></a><span data-ttu-id="65412-109">Para asignar un certificado a un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="65412-109">To assign a certificate to a send port</span></span>  
  
1.  <span data-ttu-id="65412-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="65412-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="65412-111">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea asignar un certificado a un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="65412-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to assign a certificate to a send port.</span></span>  
  
3.  <span data-ttu-id="65412-112">Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **certificado**.</span><span class="sxs-lookup"><span data-stu-id="65412-112">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificate**.</span></span>  
  
4.  <span data-ttu-id="65412-113">Si el certificado existe en el equipo local, haga clic en **examinar**, busque el certificado que desea asignar a este puerto de envío y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="65412-113">If the certificate exists on the local computer, click **Browse**, browse to the certificate that you want to assign to this send port, and then click **OK**.</span></span> <span data-ttu-id="65412-114">De lo contrario, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="65412-114">Otherwise, skip this step.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65412-115">Aun si el certificado existe en el equipo local, también debe existir en el equipo en el que se ejecute BizTalk Server (si no es el mismo que el primero) antes de que el puerto de envío pueda procesar mensajes.</span><span class="sxs-lookup"><span data-stu-id="65412-115">Even if the certificate exists on the local computer, it must also exist on the computer running BizTalk Server, if different, before the send port will be able to process messages.</span></span>  
  
5.  <span data-ttu-id="65412-116">Si el certificado no existe en el equipo local, en la **huella digital** , escriba o pegue la huella digital del certificado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="65412-116">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="65412-117">La huella digital de certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="65412-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65412-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="65412-118">See Also</span></span>  
 [<span data-ttu-id="65412-119">Crear y configurar puertos de envío</span><span class="sxs-lookup"><span data-stu-id="65412-119">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)